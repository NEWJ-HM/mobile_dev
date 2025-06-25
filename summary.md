# モバイルアプリ教科書まとめ
<details>
<summary>UIウィジェット</summary>  
  
# Text  
・文字を表示する基本ウィジェット 
<details>
<summary>使い方</summary> 
Text　(<br>
  'こんにちは Flutter!',<br>
  style: TextStyle(fontSize: 24, color: Colors.blue),<br>
)<br>
</details>
  
# Container  
・余白、サイズ、装飾などをまとめて指定できる箱  
<details>
<summary>使い方</summary>
Container(<br>
  padding: EdgeInsets.all(16),<br>
  color: Colors.amber,<br>
  child: Text('中にテキストがあります'),<br>
)  
</details>  

# Row / Column
・水平方向・垂直方向にウィジェットを並べる 
<details>
<summary>使い方</summary>  
Row(  
  mainAxisAlignment: MainAxisAlignment.center,<br>
  children: [<br>
    Text('左'),<br>
    SizedBox(width: 10),<br>
    Text('右'),<br>
  ],<br>
) <br>

Column(<br>
  mainAxisAlignment: MainAxisAlignment.center,<br>
  children: [<br>
    Text('上'),<br>
    SizedBox(height: 10),<br>
    Text('下'),<br>
  ],<br>
)
</details>  

# Image  
・画像を表示（ネット・アセット両対応）  
<details>
<summary>使い方</summary>
・ネット<br>
Image.network(<br>
  'https://example.com/image.png',<br>
  width: 100,<br>
  height: 100,<br>
)<br>

・アセット<br>
Image.asset(<br>
  'assets/sample.png',<br>
  width: 100,<br>
  height: 100,<br>
)
</details>

# Icon  
・アイコン表示用  
<details>
<summary>使い方</summary>
Icon(<br>
  Icons.favorite,<br>
  color: Colors.red,<br>
  size: 48,<br>
)  
</details>

# ElevatedButton  
・押すと反応するボタン 
<details>
<summary>使い方</summary>
ElevatedButton(  
  onPressed: () {<br>
    print('ボタンが押されました');<br>
  },<br>
  child: Text('クリック'),<br>
)<br>
</details>

# Scaffold  
・AppBar、ボディなどをまとめた画面の土台　
<details>
<summary>使い方</summary>
Scaffold(<br>
  appBar: AppBar(<br>
    title: Text('タイトルバー'),<br>
  ),<br>
  body: Center(<br>
    child: Text('ここが本文エリア'),<br>
  ),<br>
)
</details>

# AppBar  
・画面上部のバー（タイトルやアクションを表示）
#### 使い方  
AppBar(  
  title: Text('アプリのタイトル'),  
  backgroundColor: Colors.green,  
)  
# SizedBox  
・スペース（幅や高さ）を空けたいときに使う
#### 使い方  
SizedBox(  
  height: 20,  
)  
# Center  
・子ウィジェットを中央に配置するためのウィジェット  
#### 使い方  
Center(  
  child: Text('中央揃えのテキスト'),  
)  
# Padding  
・子ウィジェットの内側に余白を追加するウィジェット  
#### 使い方  
Padding(  
  padding: EdgeInsets.all(16),  
  child: Text('余白付きテキスト'),  
)  
# Checkbox  
・オン／オフ状態（チェック）を持つウィジェット 
#### 使い方  
bool isChecked = false;  
  
Checkbox(  
  value: isChecked,  
  onChanged: (bool? value) {  
    setState(() {  
      isChecked = value!;  
    });  
  },  
)  

</details>
