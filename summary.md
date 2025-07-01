# モバイルアプリ教科書まとめ
<details>
<summary>ウィジェット</summary> 
  <details><summary>基本ウィジェット</summary>

  # Text  
・文字を表示する基本ウィジェット 
<details>
<summary>使い方</summary> 

    Text　(
      'こんにちは Flutter!',
      style: TextStyle(fontSize: 24, color: Colors.blue),
    )
</details>

# Image  
・画像を表示（ネット・アセット両対応）  
<details>
<summary>使い方</summary>
・ネット<br>
  
    Image.network(
    'https://example.com/image.png',
    width: 100,
    height: 100,
    )

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

  </details>

  <details>
    <summary>状態、アクションウィジェット</summary>
  </details>

  <details>
    <summary>ユーザー入力ウジェット</summary>
  </details>

  <details>
    <summary>レイアウトウィジェット</summary>
  </details>

  <details>
    <summary>画面構造系ウィジェット</summary>
  </details>

  <details>
    <summary>スクロールリスト系ウィジェット</summary>
  </details>

  <details>
    <summary>ダイアログ、通知系ウィジェット</summary>
  </details>

  <details>
    <summary>装飾、レイアウト補助ウィジェット</summary>
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



# ElevatedButton  
・押すと反応する立体ボタン 
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
<details>
<summary>使い方</summary>  
AppBar(  <br>
  title: Text('アプリのタイトル'),  <br>
  backgroundColor: Colors.green,  <br>
)  <br>
</details>

# SizedBox  
・スペース（幅や高さ）を空けたいときに使う
<details>
<summary>使い方</summary>  
SizedBox(  <br>
  height: 20,  <br>
)  <br>
  </details>
  
# Center  
・子ウィジェットを中央に配置するためのウィジェット  
<details>
  <summary>使い方</summary>
Center(  <br>
  child: Text('中央揃えのテキスト'),  <br>
)  <br>
</details>

# Padding  
・子ウィジェットの内側に余白を追加するウィジェット  
<details>
<summary>使い方</summary>
Padding(  <br>
  padding: EdgeInsets.all(16),  <br>
  child: Text('余白付きテキスト'),  <br>
)  <br>
</details>

# Checkbox  
・オン／オフ状態（チェック）を持つウィジェット 
<details>
<summary>使い方</summary> 
bool isChecked = false;  <br>
  
Checkbox(  <br>
  value: isChecked,  <br>
  onChanged: (bool? value) {  <br>
    setState(() {  <br>
      isChecked = value!;  <br>
    });  <br>
  },  <br>
)  <br>
</details>

# Switch
・ON/OFFを切り替えるスイッチ型ウィジェット

<details> <summary>使い方</summary> bool isOn = false; <br>
Switch( <br>
value: isOn, <br>
onChanged: (bool value) { <br>
setState(() { <br>
isOn = value; <br>
}); <br>
}, <br>
) <br>

</details>

# Slider
・数値をスライドで選択できるウィジェット

<details> <summary>使い方</summary> double sliderValue = 50; <br>
Slider( <br>
min: 0, <br>
max: 100, <br>
value: sliderValue, <br>
onChanged: (double value) { <br>
setState(() { <br>
sliderValue = value; <br>
}); <br>
}, <br>
) <br>

</details>

# TextField
・テキストをユーザーが入力するためのフィールド

<details> <summary>使い方</summary> final myController = TextEditingController(); <br>
TextField( <br>
controller: myController, <br>
decoration: InputDecoration(labelText: '名前'), <br>
) <br>

</details>

# DropdownButton
・選択肢から1つを選ぶドロップダウンメニュー

<details>
  <summary>使い方</summary> 
  String selected = '選択肢1'; <br> 
  DropdownButton<String>( <br> 
    value: selected, <br> 
    items: ['選択肢1', '選択肢2'] <br> 
    .map((e) => DropdownMenuItem(value: e, child: Text(e))) <br> 
    .toList(), <br>
    onChanged: (value) { <br>
    setState(() { <br>
    selected = value!; <br>
    }); <br>
    }, <br>
    ) <br>
  </details>

  # Radio
・複数の中から1つだけ選べるラジオボタン

<details> <summary>使い方</summary> String selected = 'A'; <br>
Radio( <br>
value: 'A', <br>
groupValue: selected, <br>
onChanged: (value) { <br>
setState(() { <br>
selected = value!; <br>
}); <br>
}, <br>
) <br>

</details>

# ListView
・縦方向に複数のウィジェットをスクロール表示する

<details> 
  <summary>使い方</summary> 
  ListView( <br>
  children: [ <br> 
  Text('項目1'), <br>
  Text('項目2'), <br>
  Text('項目3'), <br>
  ], <br>
  ) <br>
</details>

# Card
・角丸＋影付きのコンテナ（情報カード風）

<details>
  <summary>使い方</summary> 
  Card( <br>
  elevation: 4, <br>
  child: Padding( <br>
  padding: EdgeInsets.all(16), <br>
  child: Text('カードの中身'), <br>
  ), <br>
  ) <br>
</details>

# Divider
・線を引いてUIの区切りを作るウィジェット

<details>
  <summary>使い方</summary> 
  Divider( <br> 
  color: Colors.grey, <br>
  thickness: 1, <br>
  indent: 16, <br>
  endIndent: 16, <br> 
  ) <br>
</details>

# RichText
・複数のスタイルを組み合わせたテキストを表示する

<details>
  <summary>使い方</summary>
  RichText( <br>
  text: TextSpan( <br>
  style: TextStyle(fontSize: 18, color: Colors.black), <br>
  children: [ <br>
  TextSpan(text: 'こんにちは、'), <br> 
  TextSpan( <br> text: 'Flutter', <br>
  style: TextStyle(fontWeight: FontWeight.bold, color: Colors.blue), <br>
  ), <br>
  TextSpan(text: '！'), <br>
  ], <br>
  ), <br>
  ) <br>
</details>

# TextButton
・背景のないフラットなボタン（リンク風に見える）

<details>
  <summary>使い方</summary> 
  TextButton( <br> 
  onPressed: () { <br>
  print('TextButtonが押されました'); <br> 
  }, <br> 
  child: Text('押す'), <br>
  ) <br>
</details>

# IconButton
・アイコンだけのボタン（小さめの操作に便利）

<details> 
  <summary>使い方</summary> 
  IconButton( <br>
  icon: Icon(Icons.thumb_up), <br>
  color: Colors.blue, <br>
  onPressed: () { <br>
  print('いいねされました'); <br>
  }, <br>
  ) <br>
</details>

# FloatingActionButton
・画面右下に配置される丸いボタン（アクション強調に使う）

<details>
  <summary>使い方</summary>
  FloatingActionButton( <br>
  onPressed: () { <br>
  print('追加されました'); <br>
  }, <br>
  child: Icon(Icons.add), <br>
  backgroundColor: Colors.green, <br>
  ) <br>
</details>

# Checkbox
・オン／オフを切り替えるチェック用ウィジェット

<details> <summary>使い方</summary> bool isChecked = false; <br>
Checkbox( <br>
value: isChecked, <br>
onChanged: (bool? value) { <br>
setState(() { <br>
isChecked = value!; <br>
}); <br>
}, <br>
) <br>

</details>


</details>
