## html 띄우기

### 1.만들고 싶은 html 파일을 앱 안에 만든다.
: 이때 앱의 이름이 `hi`라면 그 안에 `templates`폴더를 만들고 그 폴더 안에 앱의 이름과 같은 `hi`폴더를 만들어준다.
> ex) `hi/templates/hi`

<br>

### - 앱 이름과 같은 폴더를 `templates폴더` 안에 하나 더 만들어 주는 이유는?
: `render` 함수를 통해 html 파일을 가져올 때 `templates` 폴더 안에서 파일을 가져오는데  
  만약 다른 앱에 이름이 동일한 다른 html 파일이 있다면 그 html 파일을 불러올 수 있기 때문에  
  `hi/main.html` 이렇게 명확히 적을 수 있도록 하기 위함이다.
  
<br>

### 2. 앱의 `views.py`에서 함수 또는 클래스를 만들어 준다.
```python
def main(request):
  return render(request, '폴더명/main.html')
```
:`templates`안의 html 파일을 `render`를 통해 view로 보낸다.

<br>

### 3. 경로를 생성한다.
: 앱의 `urls.py`에서 경로를 지정해야 한다.  
- 서버를 실행시켰을 때 첫 페이지에 html 파일을 띄우고 싶으면  
  `path('', 경로)` : 이렇게 빈 칸('')으로 적는다.
  
- 경로를 불러오기 위해 views.py에 만들어 둔 main 함수를 불러온다.  
`from 폴더명.views import main`  
: 이렇게 불러온 뒤에 `path('', main)` 이렇게 함수명을 적어주면 된다.  
  그러면 views.py에 적어둔 `main` 함수대로 `폴더명/main.html`로 이동하게 되어 첫 페이지에 html 파일을 띄울 수 있다.
  
<br>

#### +) 도메인과 경로
: ex) `naver.com` - 도메인  
      `/../../` - 경로  
      `url` = 도메인과 경로로 이루어짐


