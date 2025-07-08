# モバイルアプリ教科書まとめ 
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

    Image.asset(
      'assets/sample.png',
      width: 100,
      height: 100,
    )
</details>

# Icon  
・アイコン表示用  
<details>
<summary>使い方</summary>
  
    Icon(
      Icons.favorite,
      color: Colors.red,
      size: 48,
    )  
</details>

# Divider
・線を引いてUIの区切りを作るウィジェット

<details>
<summary>使い方</summary> 
  
    Divider(
    color: Colors.grey,
    thickness: 1, 
    indent: 16, 
    endIndent: 16, 
    ) 
</details>

# RichText
・複数のスタイルを組み合わせたテキストを表示する

<details>
  <summary>使い方</summary>
  
    RichText( 
    text: TextSpan( 
    style: TextStyle(fontSize: 18, color: Colors.black), 
    children: [ 
    TextSpan(text: 'こんにちは、'), 
    TextSpan( <br> text: 'Flutter', 
    style: TextStyle(fontWeight: FontWeight.bold, color: Colors.blue), 
    ), 
    TextSpan(text: '！'), 
    ], 
    ), 
    ) 
</details>

</details>

-------------------------------------------

<details>
<summary>状態、アクションウィジェット</summary> 

# ElevatedButton
・押すと反応する立体ボタン

<details>
<summary>使い方</summary>
  
    ElevatedButton(  
    onPressed: () {
    print('ボタンが押されました');
    },
    child: Text('クリック'),
    )

</details>

# TextButton
・背景のないフラットなボタン（リンク風に見える）

<details>
  <summary>使い方</summary> 
  
    TextButton( 
    onPressed: () { 
    print('TextButtonが押されました'); 
    }, 
    child: Text('押す'), 
    ) 
    
</details>

# IconButton  
・アイコンだけのボタン（押すとアイコンに反応が出る）

<details>  
  <summary>使い方</summary>  

  　IconButton(  
    onPressed: () {  
    print('IconButtonが押されました');  
    },  
    icon: Icon(Icons.favorite),  
  　)
</details> 

## FloatingActionButton  
・画面上に浮かぶ丸いボタン。通常は画面の右下に配置される。

<details>  
  <summary>使い方</summary>  

  　FloatingActionButton(
    onPressed: () {
    print('FloatingActionButtonが押されました');
    },
    child: Icon(Icons.add),
  　)
</details> 

# Checkbox
・オン／オフを切り替えるチェック用ウィジェット

<details> 
  <summary>使い方</summary> 

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

# Switch
・ON/OFFを切り替えるスイッチ型ウィジェット

<details> 
    <summary>使い方</summary> 
    
    bool isOn = false; 
    Switch( 
    value: isOn, 
    onChanged: (bool value) { 
    setState(() { 
    isOn = value; 
    }); 
    }, 
    ) 

</details>

# Slider
・数値をスライドで選択できるウィジェット

<details> 
  <summary>使い方</summary> 
  
    double sliderValue = 50; 
    Slider( 
    min: 0, 
    max: 100, 
    value: sliderValue, 
    onChanged: (double value) { 
    setState(() { 
    sliderValue = value; 
    }); 
    }, 
    ) 

</details>


</details>

-------------------------------------------

  <details>
    <summary>ユーザー入力ウジェット</summary>

# TextField
・テキストをユーザーが入力するためのフィールド

<details> 
  <summary>使い方</summary>
  
    final myController = TextEditingController(); 
    TextField( 
    controller: myController, 
    decoration: InputDecoration(labelText: '名前'), 
    ) 

</details>

# TextFormField  
・テキスト入力用のフォームウィジェット。バリデーションや装飾も可能。

<details>  
  <summary>使い方</summary>  

    　TextFormField(
      decoration: InputDecoration(
      labelText: '名前',
      border: OutlineInputBorder(),
      ),
      onChanged: (value) {
      print('入力された値: $value');
      },
    　)

</details>

# DropdownButton
・選択肢から1つを選ぶドロップダウンメニュー

<details>
<summary>使い方</summary>
  
    　String selected = '選択肢1'; 
    　DropdownButton<String>( 
      value: selected, 
      items: ['選択肢1', '選択肢2'] 
      .map((e) => DropdownMenuItem(value: e, child: Text(e))) 
      .toList(), 
      onChanged: (value) { 
      setState(() { 
      selected = value!; 
      }); 
      }, 
      ) 
</details>

## Radio  
・複数の選択肢から1つだけ選べる丸ボタン。グループ化して使う。

<details>
  <summary>使い方</summary>

    int _selectedValue = 1;
    
    Column(
      children: [
        Radio<int>(
          value: 1,
          groupValue: _selectedValue,
          onChanged: (value) {
            print('1が選ばれました');
          },
        ),
        Radio<int>(
          value: 2,
          groupValue: _selectedValue,
          onChanged: (value) {
            print('2が選ばれました');
          },
        ),
      ],
    )

</details> 

## Form  
・複数の入力フィールドをまとめてバリデーション（検証）するためのウィジェット。

<details>
  <summary>使い方</summary>

    final _formKey = GlobalKey<FormState>();
    
    Form(
      key: _formKey,
      child: Column(
        children: [
          TextFormField(
            decoration: InputDecoration(
              labelText: 'ユーザー名',
              border: OutlineInputBorder(),
            ),
            validator: (value) {
              if (value == null || value.isEmpty) {
                return 'ユーザー名を入力してください';
              }
              return null;
            },
          ),
          SizedBox(height: 16),
          ElevatedButton(
            onPressed: () {
              if (_formKey.currentState!.validate()) {
                print('バリデーション成功！');
              } else {
                print('バリデーション失敗');
              }
            },
            child: Text('送信'),
          ),
        ],
      ),
    )
</details>

</details>

  -------------------------------------------

  <details>
    <summary>レイアウトウィジェット</summary>

# Row / Column
・水平方向・垂直方向にウィジェットを並べる 
<details>
<summary>使い方</summary>  
  
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

</details>  

# Stack  
・ウィジェットを重ねて表示する。

<details>
  <summary>使い方</summary>

    Stack(
      children: [
        Container(
          width: 100,
          height: 100,
          color: Colors.blue,
        ),
        Container(
          width: 60,
          height: 60,
          color: Colors.red,
        ),
      ],
    )
</details>

# Expanded  
・余っているスペースを自動で広がって埋めてくれるウィジェット（主に Row や Column の中で使う）。

<details>
  <summary>使い方</summary>

    Row(
      children: [
        Container(
          width: 50,
          height: 50,
          color: Colors.red,
        ),
        Expanded(
          child: Container(
            height: 50,
            color: Colors.blue,
          ),
        ),
      ],
    )

</details>

# Flexible  
・`Expanded` に似ているが、子ウィジェットのサイズを「最大限広げる」ことができ、必要なら縮むこともできる。

<details>
  <summary>使い方</summary>

    Row(
      children: [
        Container(
          width: 50,
          height: 50,
          color: Colors.red,
        ),
        Flexible(
          child: Container(
            height: 50,
            color: Colors.green,
          ),
        ),
      ],
    )

</details>

# Spacer  
・`Row` や `Column` の中で空きスペースを作って、ウィジェットの間に余白を入れるためのウィジェット。

<details>
  <summary>使い方</summary>

    Row(
      children: [
        Icon(Icons.star),
        Spacer(),
        Icon(Icons.star),
      ],
    )

</details>

# SizedBox  
・指定した幅・高さの空間を作ったり、ウィジェットのサイズを固定したりするためのウィジェット。

<details>
  <summary>使い方（かんたんな例）</summary>

    SizedBox(
      width: 100,
      height: 50,
      child: Container(
        color: Colors.blue,
      ),
    )

</details>

# Align  
・子ウィジェットを親の中で指定した位置に配置するためのウィジェット。

<details>
  <summary>使い方</summary>

    Align(
      alignment: Alignment.topRight, // 右上に配置
      child: Container(
        width: 100,
        height: 100,
        color: Colors.red,
      ),
    )

</details>

# Center  
・子ウィジェットを中央に配置するためのウィジェット  
<details>
  <summary>使い方</summary>
  
    Center( 
      child: Text('中央揃えのテキスト'), 
    ) 

</details>

# Padding  
・子ウィジェットの内側に余白を追加するウィジェット  
<details>
<summary>使い方</summary>
  
    Padding(
      padding: EdgeInsets.all(16),
      child: Text('余白付きテキスト'),
    )

</details>

# Container  
・余白、サイズ、装飾などをまとめて指定できる箱  
<details>
<summary>使い方</summary>
  
    Container(
      padding: EdgeInsets.all(16),
      color: Colors.amber,
      child: Text('中にテキストがあります'),
    )  
    
</details>

# Margin（Flutterでの実装例）  
・ウィジェットの外側に余白（マージン）をつけるには `Container` の `margin` を使うか、`Padding` を使う。

<details>
  <summary>使い方（Containerのmargin）</summary>

    Container(
      margin: EdgeInsets.all(16), // 全方向に16ピクセルのマージン
      color: Colors.blue,
      child: Text('マージン付きのテキスト'),
    )
    
</details>
</details>

  -------------------------------------------

  <details>
    <summary>画面構造系ウィジェット</summary>

# Scaffold  
・マテリアルデザインの基本的な画面構造を作るためのウィジェット。 
・AppBar、ボディなどをまとめた画面の土台　
・AppBar、Drawer、FloatingActionButton、Bodyなどを簡単に配置できる。

<details>
  <summary>使い方</summary>

    Scaffold(
      appBar: AppBar(
        title: Text('タイトル'),
      ),
      body: Center(
        child: Text('こんにちは、Scaffold！'),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          print('FABが押されました');
        },
        child: Icon(Icons.add),
      ),
    )

</details>

# AppBar  
・画面上部のバー（タイトルやアクションを表示）
<details>
<summary>使い方</summary>  
  
    AppBar(  
      title: Text('アプリのタイトル'), 
      backgroundColor: Colors.green,  
    ),
  
</details>

# BottomNavigationBar  
・画面下部にタブのようなナビゲーションバーを表示するウィジェット。  
・複数のアイコンやテキストで画面切り替えに使う。

<details>
  <summary>使い方</summary>

    int _selectedIndex = 0;
    
    BottomNavigationBar(
      currentIndex: _selectedIndex,
      onTap: (int index) {
        print('選択されたタブ: $index');
        // setState(() {
        //   _selectedIndex = index;
        // });
      },
      items: const [
        BottomNavigationBarItem(
          icon: Icon(Icons.home),
          label: 'ホーム',
        ),
        BottomNavigationBarItem(
          icon: Icon(Icons.search),
          label: '検索',
        ),
        BottomNavigationBarItem(
          icon: Icon(Icons.person),
          label: 'プロフィール',
        ),
      ],
    )

</details>

# Drawer  
・画面の左端からスライドして出てくるメニュー用のサイドバー。  
・`Scaffold` の `drawer` プロパティにセットして使う。

<details>
  <summary>使い方</summary>

    Scaffold(
      appBar: AppBar(
        title: Text('Drawerの例'),
      ),
      drawer: Drawer(
        child: ListView(
          padding: EdgeInsets.zero,
          children: [
            DrawerHeader(
              decoration: BoxDecoration(
                color: Colors.blue,
              ),
              child: Text(
                'メニュー',
                style: TextStyle(
                  color: Colors.white,
                  fontSize: 24,
                ),
              ),
            ),
            ListTile(
              leading: Icon(Icons.home),
              title: Text('ホーム'),
              onTap: () {
                print('ホームが選ばれました');
              },
            ),
            ListTile(
              leading: Icon(Icons.settings),
              title: Text('設定'),
              onTap: () {
                print('設定が選ばれました');
              },
            ),
          ],
        ),
      ),
      body: Center(child: Text('メイン画面')),
    )

</details>

# TabBar / TabBarView  
・タブで画面やコンテンツを切り替えるウィジェット。  
・`DefaultTabController` でまとめて管理するのが一般的。
| 比較項目       | `TabBar`                 | `TabBarView`                    |
| ---------- | ------------------------ | ------------------------------- |
| **役割**     | タブ（見出し）を表示する             | 各タブに対応した内容（ページ）を表示する            |
| **表示位置**   | 通常は `AppBar` の下          | `Scaffold` の `body` に表示されることが多い |
| **見た目**    | タブの一覧（テキストやアイコン）         | タブごとのコンテンツ（中身）                  |
| **連携方法**   | インデックスで `TabBarView` と連動 | `TabBar` の選択に応じて自動で内容を切り替える     |
| **単体利用**   | 単体では切り替えはできない（表示だけ）      | 単体では制御できない（切り替えのきっかけが必要）        |
| **よく使う場所** | `AppBar` の `bottom:` に設定 | `Scaffold` の `body:` に設定        |


<details>
  <summary>使い方</summary>

    DefaultTabController(
      length: 3, // タブの数
      child: Scaffold(
        appBar: AppBar(
          title: Text('TabBarの例'),
          bottom: TabBar(
            tabs: [
              Tab(icon: Icon(Icons.home), text: 'ホーム'),
              Tab(icon: Icon(Icons.search), text: '検索'),
              Tab(icon: Icon(Icons.settings), text: '設定'),
            ],
          ),
        ),
        body: TabBarView(
          children: [
            Center(child: Text('ホーム画面')),
            Center(child: Text('検索画面')),
            Center(child: Text('設定画面')),
          ],
        ),
      ),
    )

</details>


</details>

  -------------------------------------------

  <details>
    <summary>スクロールリスト系ウィジェット</summary>

# SingleChildScrollView  
・1つのウィジェット（子）をスクロール可能にする。  
・内容が画面より大きいときに、縦や横にスクロールさせたい場合に使う。

<details>
  <summary>使い方（かんたんな縦スクロール）</summary>

    SingleChildScrollView(
      child: Column(
        children: [
          Container(height: 200, color: Colors.red),
          Container(height: 200, color: Colors.green),
          Container(height: 200, color: Colors.blue),
          Container(height: 200, color: Colors.orange),
        ],
      ),
    )

</details>

# ListView
・縦方向に複数のウィジェットをスクロール表示する

<details> 
  <summary>使い方</summary> 
  
      ListView(
      children: [
      Text('項目1'), 
      Text('項目2'),
      Text('項目3'),
      ],
      )
      
</details>


</details>

  -------------------------------------------

  <details>
    <summary>ダイアログ、通知系ウィジェット</summary>
  </details>

  -------------------------------------------

  <details>
    <summary>装飾、レイアウト補助ウィジェット</summary>
  </details>

  -------------------------------------------


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
