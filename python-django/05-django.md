## 링크를 눌러서 페이지 이동하기
### 새로운 앱 만들기
: `python manage.py startapp 이름`

- 프로젝트와 같은 이름의 폴더의 `settings.py`에서 새로 만든 앱을 추가하고 새로만든 앱에 html 파일들을 추가  
  
  : ex) `movie/templates/movie`에 `main.html`추가  
  
<br>

### 새로운 앱의 views.py에 함수 만들기
```python
def main(request):
  return render(request, 'lovely/main.html')
```

<br>

### urls.py에 경로 설정하기
```python
from movie.views import main

path('main/', main)
```
<br>

### **include**로 url 관리하기
: urls.py에 include 추가
```python
from django.urls path, include //추가

path('movie/', include('movie.urls'))
```
>movie에 대한 경로는 앞으로 movie의 urls.py에서 관리하겠다는 뜻

새로 만든 앱 movie에 urls.py파일을 추가한다.
```python
from django.urls import path //추가
from .views import main

urlpatterns = [
  path('main/', main)
]
```
이제 도메인 뒤에도 `/main`이 아닌 `/movie/main`이 붙게 된다. (시작 경로가 movie 이므로)


<br>

### a href
- **main.html** 
```python
<a href="#"> hi </a>
```
#부분에 경로를 넣어준다.  
ex)`<a href="/movie/main"> hi </a>`  

하지만 페이지 수가 많아질 경우 모든 원시 경로를 입력하기 어렵다.  
따라서 앱의 이름과 경로의 이름을 설정해서 간단하게 만든다.

<br>

- **movie의 urls.py**
```python
app_name="movie"

urlpatterns=[
  path('main/', main, name="main")
]
```

<br>

- **main.html로 돌아가서 경로를 다시 적어주면 된다.**
```python
<a href='{%url "movie:main"%}'> main </a>
```
: movie 안의 main으로 이동하라는 뜻












