## 1. AppCompatActivity
### 1. AppCompatActivity의 상속
![image](https://miro.medium.com/max/1400/1*NRMD4CaqNlhYqR-jHkbPtg.png)
1. Activity는 위와 같은 상속구조를 가지며 최종적으로는 AppCompatActivity까지 자식을 가지고 있다.

### 2. AppCompatActivity의 특징
1. setSupportActionBar(Toolbar) API를 사용하여 action item, navigation mode 등을 포함하는 action bar를 지원합니다.
2. Theme.AppCompat.DayNight 테마를 사용하며 AppCompatDelegate.setDefaultNightMode(int) API를 사용하여 다크모드를 지원합니다.
3. getDrawerToggleDelegate() API를 사용하여 DrawerLayout과 통합합니다.
4. 이 클래스를 확장하는 모든 액티비티는 AppCompat 또는 해당 테마를 확장하는 테마를 사용해야합니다.
