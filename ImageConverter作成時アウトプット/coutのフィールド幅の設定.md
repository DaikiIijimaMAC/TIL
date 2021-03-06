# フィールド幅の設定

## 「cout.width」を使用する

指定した桁に合わせて出力する

- 出力する値が指定より「少ない」場合、**空白で埋める**
- 出力する値が指定より「多い」場合、**その幅に合わせる**
- 0を引数に指定すると、必要な幅を**自動的に割り当てる**
- **1度出力すると設定が無効になる**

```c++
#include <iostream>

int main(int argc, const char * argv[]) {
  
	for(int i=5;i<150;i+=5)
	{
  	std::cout.width(3);						//	フィールド幅の指定
		std::cout << i << std::endl;	//	文字の出力
	}
  
  return 0;
}
```

実行結果

```
  5
 10
 15
 20
 25
 30
 35
 40
 45
 50
 55
 60
 65
 70
 75
 80
 85
 90
 95
100
105
110
115
120
125
130
135
140
145
```

# 拡張設定

## 「cout.width」で設定した幅の空白埋めされる部分を別の文字で埋める

「fill」関数を使用することで実現できる

- 指定できるのは1文字
- **1度出力すると設定が無効になる**

```c++
#include <iostream>

int main(int argc, const char * argv[]) {

    for(int i=5;i<150;i+=5)
    {
        std::cout.width(3);                 //  フィールド幅の指定
        std::cout.fill('+');                //  空白埋め
        std::cout << i << std::endl;    //  文字の出力
    }
    return 0;
}

```

実行結果

```c++
++5
+10
+15
+20
+25
+30
+35
+40
+45
+50
+55
+60
+65
+70
+75
+80
+85
+90
+95
100
105
110
115
120
125
130
135
140
145
```

# 1度出力すると設定が無効になる

出力が終わるとwidthの設定幅は無効になる

```c++
#include <iostream>

int main(int argc, const char * argv[]) {

    std::cout.width(3);                 //  フィールド幅の指定
    std::cout.fill('+');                //  空白埋め

    for(int i=5;i<150;i+=5)
    {
        std::cout << i << std::endl;    //  文字の出力
    }
    return 0;
}

```

出力結果

```c++
++5
10
15
20
25
30
35
40
45
50
55
60
65
70
75
80
85
90
95
100
105
110
115
120
125
130
135
140
145
```

# 