## 8. Retrofit
### 1. 어노테이션
1. @Query
    1. URL에 덧붙여 진다.
    @GET("/posts") 
    Call< List< ResponseGet>> getSecond(@Query("userId") String id);
    2. url은 http://jsonplaceholder.typicode.com/posts?userId=1 가 된다.
2. @Path
    @GET("/posts/{userId}")
    Call< ResponseGet> getFirst(@Path("userId") String id);
    1. 일 때, id로 들어간 String 값을 {userId} 로 넘겨준다. 즉, url은 http://jsonplaceholder.typicode.com/posts/1 가 된다.
3. @Field
    @FormUrlEncoded    
    @POST("/login_url/")
    Call< User> login(@field("email")String email,@field("password")String password); 
    1. 서버에 데이터를 보낼 때 Request 데이터를 하나씩 지정해서 보내려면 사용한다.
    2. ContentType을 form-encoded로 지정하여 데이터를 전송해야 하므로 @FormUrlEncoded 어노테이션을 지정해줘야한다. 안하면 오류 발생
4. @Header
    1. 해더를 대상 값으로 바꿉니다.
5. @FieldMap
    1. Field 형식을 통해 넘겨주는 값들이 여러개 일 경우 FieldMap 사용한다
    2. 참고로 Retrofit에서는 Map보다 HashMap 형식을 쓰기를 권장한다.
    3. ContentType을 form-encoded로 지정하여 데이터를 전송해야 하므로 @FormUrlEncoded 어노테이션을 지정해줘야한다. 안하면 오류 발생
    @FormUrlEncoded 
    @POST("/posts") 
    Call< ResponseGet> postFirst(@FieldMap HashMap< String, Object> parameters);
    4. 여기서 String은 키 값, Object는 데이터이다.
6. @Body
    1. Request로 넘겨주는 값이 Json형식일 경우 사용한다.
    @POST("/users/")
    Call< User> signUp(@Body User user);
7. @Part
    1. Multipart 요청시 사용한다. (Post/Put)서버에 데이터를 보낼 때 Request 데이터를 하나씩 지정해서 보내려면 사용한다.
    2. 이 때 @Multipart 어노테이션 사용함으로써 multipart라는 것을 지정해줘야 한다.
    @Multipart
    @POST(MyConstant.Url.POST_PROFILE_IMAGE_UPLOAD)
    Call< String> getUpdateProfileInfo(@Part(“imageFile”) RequestBody file);
8. @PartMap
    1. Multiple 요청시 사용한다.
    2. (POST/PUT) part 형식을 통해 넘겨주는 값들이 여러개 일경우 PartMap을 사용한다.
    3. 이때 @Multipart 어노테이션 사용함으로써 multipart 라는 것을 지정해줘야한다.
    @Multipart
    @POST(MyConstant.Url.POST_PROFILE_IMAGE_UPLOAD)
    Call< String> getUpdateProfileInfo(@Part MultipartBody.Part file, @PartMap Map< String, RequestBody> info);
