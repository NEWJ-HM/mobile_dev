# モバイルアプリ教科書まとめ
<details>
<summary>3章</summary>  
  
## Text  
・文字を表示する基本ウィジェット  
#### 使い方  
Text　(  
  'こんにちは Flutter!',  
  style: TextStyle(fontSize: 24, color: Colors.blue),  
)  
## Container  
・余白、サイズ、装飾などをまとめて指定できる箱  
#### 使い方  
Container(  
  padding: EdgeInsets.all(16),  
  color: Colors.amber,  
  child: Text('中にテキストがあります'),  
)  
## Row / Column
・水平方向・垂直方向にウィジェットを並べる  
#### 使い方  
Row(  
  mainAxisAlignment: MainAxisAlignment.center,  
  children: [  
    Text('左'),  
    SizedBox(width: 10),  
    Text('右'),  
  ],  
)  

Column(  
  mainAxisAlignment: MainAxisAlignment.center,  
  children: [  
    Text('上'),  
    SizedBox(height: 10),  
    Text('下'),  
  ],  
)  
## Image  
・画像を表示（ネット・アセット両対応）  
#### 使い方  
・ネット  
Image.network(  
  'https://example.com/image.png',  
  width: 100,  
  height: 100,  
)  

・アセット  
Image.asset(  
  'assets/sample.png',  
  width: 100,  
  height: 100,  
)  
## Icon  
・アイコン表示用  
#### 使い方  
Icon(  
  Icons.favorite,  
  color: Colors.red,  
  size: 48,  
)  
## ElevatedButton  
・押すと反応するボタン  
#### 使い方  
ElevatedButton(  
  onPressed: () {  
    print('ボタンが押されました');  
  },  
  child: Text('クリック'),  
)  
## Scaffold  
・AppBar、ボディなどをまとめた画面の土台　
#### 使い方  
Scaffold(  
  appBar: AppBar(  
    title: Text('タイトルバー'),  
  ),  
  body: Center(  
    child: Text('ここが本文エリア'),  
  ),  
)  
## AppBar  
・画面上部のバー（タイトルやアクションを表示）
#### 使い方  
AppBar(  
  title: Text('アプリのタイトル'),  
  backgroundColor: Colors.green,  
)  
## SizedBox  
・スペース（幅や高さ）を空けたいときに使う
#### 使い方  
SizedBox(  
  height: 20,  
)  
## Center  
・子ウィジェットを中央に配置するためのウィジェット  
#### 使い方  
Center(  
  child: Text('中央揃えのテキスト'),  
)  
## Padding  
・子ウィジェットの内側に余白を追加するウィジェット  
#### 使い方  
Padding(  
  padding: EdgeInsets.all(16),  
  child: Text('余白付きテキスト'),  
)  
</details>
