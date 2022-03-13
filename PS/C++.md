# getline
- string 라이브러리 내에 존재.
- getline(입력스트림 오브젝트, 문자열을 저장할 string 객체, 종결 문자);
~~~ C++
string str;
getline(cin, str);
getline(cin, str, 'c'); 
//'c', 즉 구분자(delimiter)를 만날 때 까지 모든 문자열을 입력 받아 하나의 string 객체에 저장.
~~~

## 주의
- cin은 버퍼에 엔터('\n')를 남긴다. getline은 입력 버퍼에서 문자를 가져오는데, 이 과정에서 cin이 넣어둔 엔터를 가져오게 되면 표면상으론 getline이 입력을 받지 않는 것 처럼 보인다. 
- 이를 해결하기 위해 cin 이후 getline을 사용할 때에는 cin.ignore()를 사용해줘야 한다.
~~~C++
// cin.ignore()를 사용하지 않을 경우
int n;
string str;
cin >> n;
getline(cin, str);
//getline은 그냥 넘어감
~~~
~~~C++
// cin.ignore()를 사용할 경우
int n;
string str;
cin >> n;
cin.ignore();
getline(cin, str);
//cin과 getline 모두 잘 작동함.
~~~

