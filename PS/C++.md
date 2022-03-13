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
<br></br>
# cin.eof()
- 모든 파일의 끝에는, 우리가 눈으로 볼 수는 없으나 EOF(End Of File)라는 표시가 붙어 있다.
- cin으로 입력을 받으려 할 때 EOF가 읽히면 입력 받기가 취소되고 cin.eof()가 true가 나온다.
- 터미널에서 직접 입력을 할 땐 EOF를 수동으로 넣어줘야 한다.
- 윈도우에서는 Ctrl + Z, 유닉스에서는 Ctrl + D 이다.
- BOJ에서는 입력을 넣을 때 파일로 주기 때문에 EOF가 붙어있다.
- xcode는 Ctrl + D 를 입력하면 엔터를 누르지 않아도 바로 eof로 받아들이게 된다.
~~~C++
for(int i =0;i < 100;i ++){
    string str;
    getline(cin, str);
        
    if(str == "")
        return 0;
        
    cout<<str<<"\n";
}
~~~
```C++
int n;
    cin>>n;
    if(cin.eof())
        cout<< "eof!\n";
    else
        cout<< n;
```
