## Admin 페이지

: 내가 만든 새로운 모델을 admin 페이지에서 관리하는 것이 목표이다.

<br>

### admin 페이지의 superuser 계정 만들기
`python manage.py createsuperuser`  
: username, email address, password를 설정한다.

<br>

### 앱의 admin.py
`from .models import 모델명`  
: **.models**는 같은 앱의 models를 의미함

<br>

### admin 페이지 꾸며주기
```
class 이름(admin.ModelAdmin):
  list_display= ('id', 'title', 'view_count', 'created_at', 'updated_at')
```
: list_display는 column들을 테이블 형태로 보여준다.

<br>

### 검색 기능 추가
`search_fields= ('title')`  
:title로 검색 가능
