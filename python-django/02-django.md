### 앱 생성하기
`python manage.py startapp 이름`  
: 앱을 생성한 뒤 **settings.py**의 **installed_apps**에 앱 이름을 추가해야 한다.

<br>

### 생성한 앱의 models.py에서 모델링
```
class 모델명(models.Model):
  title= models.CharField(max_length=100)
  content= models.TextField()
  view_count= models.IntegerField(default=0)
  created_at= models.DateTimeField(auto_now_add=True)
  updated_at= models.DateTimeField(auto_now=True)
```

<br>

### 주문서 만들기
`python manage.py makemigrations`

<br>

### 주문서 내역을 실제로 테이블 형태로 만들기
`python manage.py migrate`

<br>

### shell에서 객체 생성 및 조회
`python manage.py shell`
`from 앱 이름.models import 모델명`

<br>

### 객체 생성하기
- `모델명.objects.create(title="...", content="...")` 
- `새로운 변수명 = 모델명.objects.get(id=1)`  
(id=1에 담긴 내용을 새로운 변수에 담는다.)
- `변수명.title`
(id=1의 title 출력)
<br>

`모델명.objects`가 반복되므로  
>`a= 모델명.objects`  
`a.create()`  
`a.get()`

이렇게 변수에 담아서 사용 가능하다.

<br>

### 객체 조회하기
`모델명.objects.all()`  
: 모델에 담긴 객체들의 목록을 보여줌 

`모델명.objects.value()`  
: 각 객체들의 값을 보여줌    
  (ex) title, content 등에 어떤 값이 담겼는지 보여줌)

