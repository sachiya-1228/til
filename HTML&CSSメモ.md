・見出しをつける

	見出しの要素は<h1>要素以外にも、<h2>, <h3>, ..., <h6>要素があります。 
	hはheading（見出し）の略です。
	図のように、<h1>が一番大きな見出しで、<h6>が一番小さな見出しになります。
	


・段落を作成する

	段落を表すのは<p>要素です。 
	pはparagraph（段落）の略です。
	<h2>要素や<p>要素で囲んだテキストは改行されます。

	見出し以外の文に関しては、<p>要素を用いましょう。



・HTMLのコメント

	<!-- -->で囲んだテキストのことを「コメント」と呼びます



・リンク

	リンクを作成するためには<a>要素を用います。
	テキストを<a>タグで囲むことで、簡単にリンクを作ることができます

	<a>要素にリンクの飛び先を指定するには、href属性を追加する必要があります。
	<a href="url">というように書き、url部分にリンク先のURLを指定することで、そのページへのリンクを作ることができます。


		<a href="https://prog-8.com">Progateへ</a>



・属性

	HTMLでは、hrefのような属性が数多くあります。
	これらは、図のように開始タグの中に記述します。
	値を指定する際は、ダブルクォーテーション（"）を忘れないように注意してください。



・画像の表示

	画像の表示には<img>要素を用います。
	<img src="url">のように、src属性のurlの部分に画像のリンクを指定することで、画像が表示されます。 
	<img>要素はテキストを囲むことがないため、終了タグが要りません。
	alt属性（オルト属性）とは、HTMLのimg要素の中に記述される画像の代替となるテキスト情報です。
	従って、「画像が閲覧できない環境下でも、その情報が正しく理解される」ような代替テキスト情報がalt属性には記述されなければなりません。


		<img src="https://s3-ap-northeast-1.amazonaws.com/progate/shared/images/lesson/html/study/html.svg" alt="" />



・リストの作成

	リストを作るには、<li>要素を用います。
	箇条書きにしたいテキストをそれぞれ<li>タグで囲むことで、リストを作ることができます。

	<li>要素は、囲む要素によって種類が変わるという特徴を持っています。
	<ul>要素で囲むと、黒点が先頭につきます。
	<ol>要素で囲むと、数字が連番でつきます（ここでは扱いません）。
	このように要素を要素で囲むことを入れ子と言います。
	囲む方の要素を親要素、囲まれる要素を子要素と呼びます。

	～.css

		<ul>
			<li>HTML</li>
			<li>PHP</li>
		  	<li>Ruby</li>
		</ul>


	結果
			・HTML
			・PHP	
			・Ruby



				リストの黒点を消す


					<li>要素にlist-styleプロパティを用いてnoneを指定すると、リストの先頭のマークを消すことができます。
					基本的に先頭の黒点は必要ないので、消してしまいましょう。


					stylesheet.css

						li{
							list-style:none;
						}	



・HTMLの全体構造

	実際のHTMLファイルには、決められた型を書いていく必要があります。
	図のように、<html>要素の中に<head>要素と<body>要素が必要です。
	<head>要素にはページに関する情報、<body>要素には実際に表示したい内容を書きます。
	これまで勉強してきた要素は、<body>要素の中に記述していきます。


		HTMLバージョンを指定する


					<!DOCTYPE html>の部分はDOCTYPE宣言と呼ばれるもので、HTMLのバージョンを宣言するためのものです。
					今回は最新バージョンのHTML5を使うため、<!DOCTYPE html>を使用します。

		<head>要素
		

					<head>要素にはWebページの設定に関する情報を書いていきます。
					<head>要素内に記述した内容はWebページには表示されません。


							<!-- DOCTYPE宣言を追加してください -->
							<!DOCTYPE html>

							<!-- <html>要素を追加してください -->
							<html>
					  		<head>
					 		</head>
					 		<body>
    
					  		</body>
							</html>


					<head>要素の中では、①文字コードの指定、②ページのタイトルの設定、③CSSの読み込みなどを行っていきます。
					これらは定型文のようなものなので完全に覚える必要はありませんが、どのようなものがあるのかを知っておきましょう。


					①文字コードを指定することで、ページの文字化けを防ぐことができます。 
					<meta charset="utf-8">とすることで、そのページの文字コードをUTF-8に指定することができます。 
					UTF-8は、HTML5で推奨されている文字コードです。

					②<title>要素は、ページのタイトルを指定します。 
					<title>要素で指定されたタイトルは、ブラウザのタブ上に現れます。

					③これまでProgate上では「stylesheet.css」で記述したCSSが結果に反映されていましたが、本来はHTMLの方で読み込む必要があります。
					HTMLからCSSを読み込むためには、<link rel="stylesheet">を用います。
					<link rel="stylesheet" href="stylesheet.css">のように、href属性で読み込むCSSファイルを指定します。


						<!DOCTYPE html>
							<html>
						  		<head>
									 <!-- 雛形をコピーして、3つの要素を追加してください -->
									<!-- 文字コードを「utf-8」にしてください -->
							    		<meta charset="utf-8">
    
							    		<!-- タイトルを「Progate」にしてください -->
							    		<title>Progate</title>
    
							    		<!-- 「stylesheet.css」を読み込んでください -->
							    		<link rel="stylesheet" href="stylesheet.css">
							  		</head>
							  		<body>
							  		</body>
							</html>



・レイアウト

	<div>要素
			レイアウトは<div>要素によって構成していきます。
			<div>要素の「div」は「division」の略で、要素をグループ化するために使用されます。
			「header」、「main」、「footer」というclass名を持った3つの<div>要素でレイアウトを分割しています。


				<!DOCTYPE html>
						          <html>
				  				<head>
 				  				 　<meta charset="utf-8">
 				  				 　<title>Progate</title>
 				  				 　<link rel="stylesheet" href="stylesheet.css">
				  				</head>
				  				<body>
				   				<!-- <div>要素を追加し、「header」というclassをつけてください -->
				   				<div class= "header">
		      
				    				</div>
    
				    				<!-- <div>要素を追加し、「main」というclassをつけてください -->
				   				 <div class= "main">
      
				   				 </div>
    
				    				<!-- <div>要素を追加し、「footer」というclassをつけてください -->
				    				<div class = "footer">
      
				   				 </div>
    
				  				</body>
							    </html>

	
	ヘッダーの構造


				<!DOCTYPE html>
							<html>
							  <head>
							    <meta charset="utf-8">
							    <title>Progate</title>
							    <link rel="stylesheet" href="stylesheet.css">
							  </head>
							  <body>
							    <div class="header">
							      <!-- <div>要素を追加し、「header-logo」というclassをつけてください -->
							      <div class = "header-logo">
							        Progate
							      </div>
      
							      <!-- <div>要素を追加し、「header-list」というclassをつけてください -->
							      <div class ="header-list">
							        <ul>
						  			<li>プログラミングとは</li>
							  		<li>学べるレッスン</li>
						  			<li>お問い合わせ</li>
								</ul>
							      </div>  

							    <div class="main">
      
							    </div>

							    <div class="footer">
      
							    </div>
							  </body>
							</html>



	<header>と<footer>

			<div class="header">と<div class="footer">のような、ヘッダーとフッターのためのタグは非常によく使われるので、
			HTML5は<header>と<footer>というタグが用意されています。
			<header>, <footer>を使う方が一般的なので、こちらを使いましょう。

			
				divクラスを用いたheaderの宣言

							    <div class="header">
							      <!-- <div>要素を追加し、「header-logo」というclassをつけてください -->
							      <div class = "header-logo">
							        Progate
			              			      </div>
							    </div>
      

				<header>タグを用いた宣言
		
				 			    <header>
      
							    </header>
			


	mainの構造

			メイン部分のレイアウトを作っていきましょう。 
			main要素は、「copy-container」、「contents」、「contact-form」の3つの要素で構成されています。

				参照：https://prog-8.com/html/study/1/18#/57



・CSSとは

			CSSとは、HTMLの要素に対して色、大きさ、配置などを指定し、ページをデザインするための言語です。
			CSSは、HTMLとは別のファイルに記述します。
			HTMLで用意した要素に対して、CSSを用いて「どこの」「何を」「どうする」かを指定することができます。 

			CSSのプロパティの末尾にはコロン（:）、行末には セミコロン（;） をつける必要があるので注意しましょう。



・CSSのコメント

			HTMLと同じく、CSSファイルにもコメントを記述することができます。
			CSSの場合は/* */で囲んだ行がコメントになります。


・プロパティの種類

			文字の色

					「color: #ff0000;」のように、16進数のカラーコードで色を指定します。


						h1 {
				 			 /* 文字の色を#ff0000にしてください */
				 		 	color: #ff0000;
  
						}




			文字

					文字の大きさを指定するにはfont-sizeプロパティを用います。 
					font-sizeは、px(ピクセル)という単位を用いて指定します。


					font-familyプロパティを用いると、フォントの種類を指定することができます。
					「 font-family: フォント名; 」とすることで、要素にそのフォントを適用できます。
					フォント名にスペースがある場合は、ダブルクォーテーションで囲みます。

	
						h1 {
			  				color: #ff0000;
			  				/* 文字の大きさを40pxにしてください */
			  				font-size:40px;
  
			  				/* 文字の種類をserifにしてください */
			  				 font-family:serif;
  
						}


						p {
			  				/* 文字の大きさを40pxにしてください */
			  				font-size:40px;
  
			  				/* 文字の種類を"Avenir Next"にしてください */
			  				 font-family:"Avenir Next";
  
						}



			背景色

					背景色を変えるにはbackground-colorプロパティを用います。 色の指定の方法はcolorプロパティと同様です。



			横幅、高さ

					要素の横幅、高さを変更したいときには、それぞれwidthプロパティ、heightプロパティを用います。 
					width, height共にpxで指定していきます。
					pxを書き忘れないように注意しましょう。


						h1 {
			  				color: #e6855e;
			 				font-size: 30px;
  			
							/* 背景の色を#f3f372にしてください */
			  				background-color:#f3f372;
  
			  				/* 高さを80pxにしてください */
			 				 height:80px;
  
 			 				/* 幅を200pxにしてください */
			  				width:200px;
  
						}



	特定の要素にCSSを適用

					要素にはclassを使って名前をつけることができます。
					classをつけることにより、それぞれの要素を識別し、別々のCSSを適用することができます。
					class名でCSSを指定する場合、先頭にドット「.」が必要な点に注意してください。


						index.html
			
							<h2>レッスン一覧</h2>
		
							<ul>
			  					<!-- 1つ目の<li>要素にselectedというclassを与えてください -->
  								<li class="selected">HTML</li>
  								<li>PHP</li>
			  					<li>Ruby</li>
							</ul>

						stylesheet.css

							li {
 			 					color: #444;
							}

							/* selectedの文字の色を#ff0000にしてください */
							.selected{
 			 					color:#ff0000;
							}



	文字を横並びにする

					floatプロパティを用いることで、指定した要素を横並びにすることができます。
					float: left;を指定すると要素が左から順に横に並びます。


						stylesheet.css

							li {
							  list-style: none;
							  /* floatプロパティをleftにしてください */
							  float:left;
  
							}



	要素に余白を入れる

					要素に余白を作りたい場合は、paddingを用います。
					「padding: 値;」とすると、上下左右すべての方向にその大きさの余白が追加されます。

	
					上下左右ではなく、ある方向のみに余白を指定したい場合もあります。
					その場合は、以下のように、「padding-top: 値;」などとすると、その方向のみに余白が追加されます。
					他にpadding-bottom、padding-left、padding-rightなどがあります。


					指定したい値が方向ごとに異なる場合、個別で指定する方法もありますが、まとめて書くことも可能です。
					値を4つ、スペース区切りで指定した場合、左から順に「上」「右」「下」「左」の順で適用されます。(時計回りになっている)
			

								li {
		
									padding:20px 10px 20px 10px;

								}
					

					値を2つ指定した場合、左から順に「上下」「左右」の順に適用されます。

									
								li {

									padding:20px 10px;
	
								}				



	入れ子のセレクタ

					「.header-list」の後にスペースを空けてliと続けると、「header-list」の中の<li>要素にのみCSSを適用することができます。
					これにより、ヘッダーの<li>要素とフッターの<li>要素に別々のCSSを適用することができます。

						

								.header-list li {

									  padding: 33px 20px;
									  float: left;

								}



	要素を左右に配置する

					float: leftとfloat:rightを組み合わせることで、ロゴとリスト全体を左右に配置することができます。
					左端に配置したい「footer-logo」にはfloat: left;を、右端に配置したい「footer-list」にはfloat: right;を指定しましょう。


								.footer-logo{
									  font-size:32px;
									  float:left;
								}


								/* footer-listのfloatを指定してください */
								.footer-list{
								  float:right;
								}



	文中の一部にCSSを適用させる

					文中の一部にCSSを適用させたい場合は、<span>要素で囲みます。
					<span>タグにCSSを指定することで、文字の色を一部変えています。
					<span>要素の前後には改行は入りません。前後に改行が入るタグと入らないタグに関して、次のスライドで一旦整理してみましょう。

						index.html

			 				<div class="main">
							      <!-- <div>要素を追加し、「copy-container」というclassをつけてください -->
							      <div class ="copy-container">
							       <h1>HELLO WORLD<span>.</span></h1>
			 				       <h2>プログラミングの世界へようこそ</h2>
			 			        </div>


						styleshhet.css

							.copy-container span {

							  color:#ff4a4a;

							}



	ブロック要素・インライン要素

					HTMLの要素には、改行される要素と改行されない要素があります。
					前後で改行が入り、親要素の幅一杯に広がる要素をブロック要素といいます。
					<div>要素や<h1>要素、<p>要素はブロック要素です。
					それに対して、<span>要素や<a>要素のように改行されない要素をインライン要素といいます。
	

						ブロック要素の特徴
							１．要素の前後に改行が入り、ブロック要素同士縦に並ぶ
							２．横幅や高さを指定できる
							３．余白(margin,padding)が指定できる

								要素の例
								h1～h6,　p,　div,　ul(ol),　liなど


						インライン要素の特徴
							１．要素の前後に改行が入らず、インライン要素同士横に並ぶ
							２．横幅や高さを指定できない(※1)
							３．ブロックレベル要素のように上下の余白設定(margin,padding)が効かない(※2)

								要素の例
								a, span, b ,img, input



	ボーダー(枠線)をつけよう

					要素にボーダー（枠線）をつけるには、borderプロパティを用います。
					左から順に枠線の太さ、種類、色を指定して使用します。

					上下左右すべてに線を付けたい場合はborderとし、特定の場所にのみ付けたい場合は「border-bottom」のように、「border-方向」とします。
					他にborder-top、border-left、border-rightなどがあります。


							.section-title{

								  border-bottom:2px solid #dee7ec;

							}
	


	
	paddingとmargin

					余白を作るにはpaddingを使ってきましたが、paddingはborderの内側の余白を作ります。
					borderの外側に余白を作りたい場合、marginを用います。
					値の指定の方法は、paddingと同じです。

					これまで勉強してきたborder, padding, marginは、ボックスモデルという概念に基いています。
					HTMLの全ての要素には、border（初期状態では表示されない）があり、その外側の余白はmargin, 内側の余白はpaddingです。

						参照：https://prog-8.com/html/study/1/21#/66

					marginもpaddingと同様に、各方向の余白をそれぞれ指定したり、まとめて指定したりすることも可能です。


							.contents-item p {

								font-size:24px;
								margin-top:30px;

							}
		

					値を4つ、スペース区切りで指定した場合、左から順に「上」「右」「下」「左」の順で適用されます。(時計回りになっている)

			
							li {

								margin:20px 10px 20px 10px;

							}
		

					値を2つ指定した場合、左から順に「上下」「左右」の順に適用されます。



							li {

								margin:20px 10px;

							}	

	入力フォーム

					<input>要素は１行のテキスト入力を受け取るための要素です。(<input>)
					<textarea>要素は複数行のテキスト入力を受け取るための要素です(<textarea></textarea>)
					<input>要素は終了タグが不要な点に注意してください。



	送信ボタンを作ろう

					<input>要素を用います。
					<input>要素にはtype属性を指定することができ、type属性にsubmitを指定すると、入力欄ではなく、下の図のような送信ボタンになります。
					ボタンに表示されるテキストは、日本語のブラウザではデフォルトで「送信」になります。


					ボタンに表示されるテキストを変更することも可能です。
					value属性に任意の値を指定することで、ボタンに表示されるテキストを変更することができます。


 							<input class = "contact-submit" type="submit" value="送信" />



	複数のセレクタに同じCSSを指定する

					複数のセレクタをコンマ（,）で区切ることで、それらに同じCSSを適用することができます。
	

						input, textarea{
							  width:400px;
							  margin-top:10px;
							  margin-bottom:30px;
							  padding:20px;
							  font-size:18px;
							  border:1px solid #dee7ec;
						}



	背景画像を指定する

					CSSで背景画像を指定するにはbackground-imageプロパティを用います。
					background-image: url(画像のURL);のように使います。

					
						.top-wrapper{
							  padding-top:180px;
							  padding-bottom:100px;
							  background-image:url(https://prog-8.com/images/html/advanced/top.png);
							  color:white;
						}



	背景画像の大きさを指定する

					background-imageで指定された背景画像は図のように表示範囲を埋め尽くすまで、繰り返し表示される性質があります。
					background-size: cover;を指定すると、1枚の画像で表示範囲を埋め尽くすように画像の大きさが拡大縮小します。


						  .top-wrapper{
								  color:white;
								  background-size:cover;
						}



	要素を中央に配置する

					中央に寄せるためにはmarginの左右にautoを指定します。
					marginにautoを指定するときは、必ずwidthを併せて指定します。
					なお、上下のmarginにautoを指定することはできません。


						.container{
							  width:1170px;
							  margin:0 auto;
						}
						
							※例えば、lesson-wrappaerクラスという枠組みの中に、containaerクラスがあるとすると
							幅だけ指定しておいてmargin:0 auto;すれば、自動的に中心に動かすことができる。
												



	要素を透過させる

					opacityプロパティを使えば要素を透明にできます。
					透明度は0.0(完全に透明) ~ 1.0(完全に不透明)の数値で指定します。



	文字の間隔を指定する

					letter-spacingプロパティを用いることで文字の間隔を指定することができます。



						.top-wrapper h1{
							  opacity:0.7;
							  font-size:45px;
							  letter-spacing:5px
						}



	ボタン部分を作ろう

					ボタンを作っていきます。ボタンは<a>タグで指定します。
					しかし<a>タグはインライン要素であり、インライン要素にはwidthやheightが指定できないなど不便な点があります。
					


	インラインブロック

					ブロック要素とインライン要素の特徴を併せ持つインラインブロック要素というものがあります。
					インラインブロック要素はインライン要素と同様に横に並びますが、ブロック要素のように幅や高さをもちます。
	

						ブロック要素(<div>タグなど)：
								width,heght：	指定できる
								margin,padding：指定できる
								配置：縦並び


						インラインブロック要素(<div>タグなど)：
								width,heght：	指定できる
								margin,padding：指定できる
								配置：横並び


						ブロック要素(<div>タグなど)：
								width,heght：	指定できない
								margin,padding：左右のみ指定できる
								配置：横並び


	要素の変更

					<a>タグは初期状態でインライン要素になっていますが、displayプロパティを使うと、インラインブロック要素に変更することができます。
					displayプロパティはblock（ブロック要素）, inline-block（インラインブロック要素）, inline（インライン要素）を指定することができます。 


							用途例：クリックできる範囲を拡大する時など
	
								例えば、<a>タグはインライン要素なので、中身のテキストの部分しか大きさを持ちません。
								その結果、<a>タグをクリックできる範囲はテキストの部分だけになってしまいます。
								<a>タグをブロック要素にすると、大きさが親要素いっぱいに広がるので、全体をクリックできるようになります。


									.header-right a{
											  line-height:65px;
											  padding:0px 25px;
											  color:white;
											  display:block;
									}



	複数クラスの指定

					ボタンのように、「共通の部分があるが、それぞれ小さい変化をつけたいとき」にはクラスの名前を複数指定すると便利です。
					下図のように、半角スペースで区切って複数のクラスを指定することができます。 


						～.html

							<div class = "btn-wrapper">
								<a href="#" class ="btn signup">新規登録はこちら</a>
							        <p>or sign up with</p>
							        <a href="#" class ="btn facebook">Facebookで登録</a>
							        <a href="#" class ="btn twitter">Twitterで登録</a>
							</div>


						～．css

							.btn{
								  padding:8px 24px;
								  color:white;
								  display:inline-block;
								  opacity:0.8;
							}


							.signup{
								  background-color:#239b76;
							}


							.facebook{
								  background-color:#3b5998;
								  margin-right:10px;
							}



	カーソルが乗ったときにCSSを指定

					カーソルが乗ったときの状態をhoverと言います。
					CSSで、セレクタ:hoverとすることで、カーソルが乗ったときのCSSを指定することができます。 

						.btn {
							  padding: 8px 24px;
							  color: white;
							  display: inline-block;
							  opacity: 0.8;
							  /* border-radiusを4pxに指定してください */
							  border-radius:4px;
						}

						/* btnクラスにhoverしたときのCSSを指定してください */
						.btn:hover{
							  opacity:1;
						}



	角を丸める

					角を丸めるにはborder-radiusプロパティを用います。
					数字が大きいほど角が丸くなります。

						.btn {
							  padding: 8px 24px;
							  color: white;
							  display: inline-block;
							  opacity: 0.8;
							  /* border-radiusを4pxに指定してください */
							  border-radius:4px;
						}



	要素の配置を指定

					text-alignプロパティを用いることで、テキスト等のインライン要素やインラインブロック要素の配置を指定することができます。
					leftで左寄せ、centerで中央揃え、rightで右寄せに設定することができます。

						.top-wrapper {
								  padding: 180px 0 100px 0;
								  background-image: url(https://prog-8.com/images/html/advanced/top.png);
								  background-size: cover;
								  color: white;
								  /* text-alignをcenterに指定してください */
								  text-align:center;
						}



	「margin: 0 auto」と 「text-align: center」の違い

					要素を中央寄せにする方法として、margin: 0 autoとtext-align: centerを学びましたが、それらの違いを整理しましょう。
					containerクラスのように、広い範囲を囲うようなブロック要素の場合はmarginを、
					テキストやボタンのようなインライン要素・インラインブロック要素の場合はtext-alignを使うようにしましょう。

						参照：https://prog-8.com/html/study/2/6#/18



	ボタンにアイコンを付ける

					アイコンを表示するにはFont Awesomeというものを使うと便利です。
					たくさんのアイコンが用意されており、自分の気に入ったアイコンを簡単に使うことが出来ます。
					https://fontawesome.com に詳しい使い方やアイコンの一覧が載っています。

					Font Awesomeは、以下の手順で使用することができます。
						①Font AwesomeのCSSファイルを読み込む

						<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">


						②<span>タグにfaクラスとfa-アイコン名クラスを指定する
						（Font Awesomeのサイトにアイコンごとのクラス名が載っています。）
						これだけで簡単にアイコンを表示させることができます。

						 <div class="btn-wrapper">
						          <a href="#" class="btn signup">新規登録はこちら</a>
						          <p>or sign up with</p>
						          <a href="#" class="btn facebook">
						            <!-- ここに<span>タグを追加しましょう -->
 						           <span class = "fa fa-facebook"></span>
						            Facebookで登録
						          </a>
						</div>



	opacityとrgbaの違い

					これまで要素を透明にするにはopacityを用いてきました。
					しかし、opacityには要素の中身全てを透明にするという性質があります。
					背景色のみを透明にするには、rgbaというものを使う必要があります。


				rgb
					rgbaを学ぶには、まずrgbというものを理解する必要があります。
					rgbは色の指定の仕方の1つで、3つの値の組み合わせで表示する色を決めます。
					色を指定するときは今まで使用してきた#ffffffのような記法を使ってもrgbを使っても構いません。


				rgba
					
					色を透明にしたいときは色をrgbaで指定します。rgbaは4つの値をコンマ（,）区切りで入れます。
					4つ目の値が透明にする度合いで、0 ~ 1の数値で指定します（値が小さいほど透明になります）。
					opacityプロパティは要素全体を透過させますが、rgbaを使うとその色だけを透明にすることが出来ます。


						header{
							  height:65px;
							  background-color:rgba(34, 49, 52, 0.9);
						}




	アニメーションをつける

					transitionを使うとアニメーションをつけることができます。
					「変化の対象」や、「変化にかかる時間」などを指定できます。
					「変化の対象」にはcolorなどのプロパティを指定しますが、allを指定すると全てのプロパティに適用出来ます。
					transitionは多くの場合hoverと組み合わせて使います。


						.header-right {
								  float: right;
								  background-color: rgba(255, 255, 255, 0.3);
								  /* transitionを指定してください */
								  transition:all 0.5s;
						}


	行間を指定する

					line-heightプロパティを使うと、行の高さを指定することができます。 
					値が大きいほど行間が大きくなります。

					line-heightプロパティは本来行間を調整するためのプロパティですが、要素の縦方向の中央に文字を配置するのにも使えます。
					line-heightプロパティの「高さの中心」に文字が配置されるため、要素の高さとline-heightプロパティを同じ値にすると、文字がちょうど中央に配置されるようになります。


						.header-right a{
								  line-height:65px;
								  padding:0px 25px;
						}



	文字の太さを指定する

					font-weightプロパティを用いると文字の太さを変更することができます。normalまたはboldを指定します。
					<h1>~<h6>の要素は初期状態でfont-weight: bold;となっているので、font-weight: normal;と指定すれば文字が細くなります。


						.heading h2{
								  font-weight:normal;
						}


	相対的な大きさの指定

					ボックスのwidthやheightをpxではなく%で指定すると、親要素に対してどのくらいの幅や高さを持つか指定することができます。


					～.html
							 <div class="lessons">
								<!-- ここにコードを書いていきましょう -->
								<div class = "lesson">
							            <div class="lesson-icon">
							              <img src="https://prog-8.com/images/html/advanced/html.png" alt="" />
							            </div>
 						         	</div>

          
							 	<div class = "lesson">
							       	     <div class="lesson-icon">
							              <img src="https://prog-8.com/images/html/advanced/jQuery.png" alt="" />
							             </div>
							        </div>

							</div>

					～.css
							.lesson{
								  float:left;
								  width:25%;
							}



	要素同士を重ねて表示する

					HTMLの要素同士は通常重なって表示されることはありませんが、position: absolute;を使うと、要素同士を重ねて表示することが出来ます。
					サイト全体の左上部分を基準とし、そこからの位置をtopとleftを用いて指定します。また、rightやbottomを併用することも可能です。


						基準位置の変更

								position: absolute;の基準位置はサイト全体の左上部分ですが、この基準位置は変更することが出来ます。
								基準としたい親要素にposition: relative;と指定すると、その要素の左上部分が基準位置となります。


									.lesson-icon{
											  position:relative;
									}


									/* lesson-iconの中の<p>のCSSを指定してください */
									.lesson-icon p{
											 position:absolute;
											 top:90px;
											 width:100%;
											 color:white;
									}



	影をつけよう

					ボックスに影を付けるためにはbox-shadowプロパティを用います。
					左から順に水平方向、垂直方向、色となり、「影の位置」と「影の色」を指定します。

						.message {

							  /* box-shadowをつけてください */
							  box-shadow:0 7px #1a7940;
						}



	カーソルの形を変える

					cursorプロパティを用いることでマウスのカーソルが要素に乗ったときのカーソルの形を変えることができます。
					タグによってcursorが初期状態で設定されているものもあり、例えば<a>タグは初期状態でpointerが設定されています。

						.message {

							  /* カーソルの形をpointerにしてください */
							  cursor:pointer;

						}


	要素がクリックされている間だけCSSを適用

					セレクタにactiveを用いることで、要素がクリックされている間だけCSSを適用することができます。 
					セレクタ:activeというように指定します。

						.message:active {
					

						}



	CSSを打ち消そう

					box-shadow: none;とすると、影を消すことが出来ます。
					このように多くのプロパティはnoneを指定することによって消すことができます。

						.message:active {

							  box-shadow: none;
						}



	position: relative;による位置の変更

					position: relative;はposition: absolute;の基準位置を決めるために使っていましたが、要素の位置を変更するためにも使うことが出来ます。
					position: relative;をtopやleftと併用すると、その要素を本来の位置からずらせます。


						応用：ボタンをへこませよう

										クリック時に、以下の処理をすることによって、ボタンがへこんで見えるようになります。
										・box-shadowをnoneにする
										・position: relative;とtopによって影の分だけ位置を下げる

												.message:active {
								 						 position: relative;
														  top: 7px;
														  box-shadow: none;
												}



	画面上に要素を固定する
					
					position: fixed;を使うと、常に要素を画面上の指定した位置に固定させておくことができます。 
					位置は、top、left、right、bottomを使って指定します。


						要素の重なり順

									positionを使用すると要素の重なりが生じます。 
									その結果図のように、レッスン紹介部分とヘッダーが重なった時に、ヘッダーが隠れてしまいます。
									重なり順を指定して、ヘッダーが上に表示されるようにしましょう。

									z-indexプロパティは、要素の重なりの順序を指定する際に使用します。 
									z-indexは整数値で指定し、値が大きいほど上に表示されます。
									z-indexプロパティは必ずpositionプロパティと併用する必要があるので、注意しましょう。


												header {

													  /* positionプロパティをfixedに、topを0に指定してください */
													  position:fixed;
													  top:0;
  
													  /* z-indexを10に指定してください */
													  z-index:10;
												}
												
												
・レスポンシブデザインの適用

			レスポンシブデザインとは、様々なデバイスや画面サイズに合わせて、コンテンツのレイアウトを調整するためのものです。
			特にスマートフォン表示に対応したサイト制作においては必須の技術です。
			
			例えばPC版で要素の幅を1170pxに固定していると、それより画面幅が狭くなるスマホ版だと、コンテンツの一部が隠れてしまいます。
			ここにレスポンシブデザインを適用することで、画面のサイズに合わせて最適なレイアウトを組めるようになります。
			
			
			
					メディアクエリを設定しよう
				
								メディアクエリとは、ブラウザの画面サイズに応じてCSSのスタイルを設定できる手法です。
				
				
							
					メディアクエリの書き方
				
								メディアクエリは、@media (条件) { .... }という様に書きます。
								指定された条件が当てはまるときにのみ{ }内のCSSが適用されます。
				
				
				
					max-widthとmin-width
					
								メディアクエリの条件には、max-width(最大幅)、またはmin-width(最小幅)を指定できます。
								max-width: ◯◯pxと指定すると、画面幅が◯◯px以下の時にCSSを適用できます。
								min-widthはその反対となります。
				
				
				
					ブレイクポイント
					
								max-width: ◯◯px（またはmin-width: ◯◯px）のようにメディアクエリの条件を指定するとき、「◯◯px」の部分をブレイクポイントと呼びます。
								今回はスマートフォンの画面幅は670px以下、タブレットの画面幅は670px ~ 1000pxと想定して、ブレイクポイントを設定しましょう。
							
							
											h1 {
												  color: red;
											}

											@media (max-width: 1000px) {
											  h1{
												    color:blue;
											  }
											}

											@media (max-width: 670px) {
											  h1{
												    color:green;
											  }
											}
											
											
											・PC表示(1200px)では赤色
											・タブレット表示(680px)では青色
											・スマートフォン表示(350px)では緑色になる。
											
							
											
					レイアウト崩れを直す
					
								例えばitemクラスに、paddingを加えたとすると、widthが25%で指定されているため、左右のpaddingを追加すると要素の幅の合計が100%を超えてしまい、
								レイアウトが崩れてしまいます。
								このようなレイアウト崩れは、box-sizing: border-box;を用いることで防ぐことができます。
							
							
								box-sizingをborder-boxに指定すると、要素の幅(width)の合計にpaddingとborderが含まれるようになります。
								width25%,padding15px,border2pxをそのまま変換したとすると要素の幅が100%を超えて、レイアウトが崩れる
								box-sizing: border-box;を使うと、上記全てを含めてwidth25%で指定してくれる。
							
								そのため、paddingやborderを追加した時に生じるレイアウト崩れを未然に防ぐことができます
								（※ただし、marginはborder-boxでの合計値に含まれません）。
							
							
							
					全要素にCSSを適用する
								
								box-sizing: border-box;を指定するときは、*(アスタリスク)に対して指定することが推奨されています。
								*はすべての要素に対してCSSを適用したい場合に用います。
								border-boxをすべての要素に対して適用することで、レイアウトを管理しやすくなります。
							
							
											*{
												  box-sizing:border-box;  
											}
							
							
							
					viewportの設定
					
								レスポンシブデザインを適用する準備として、<head>タグ内にviewportを設定しましょう。
								viewportを設定しないと、スマートフォンやタブレットでの閲覧時にメディアクエリが正しく機能しません。
								ただし、ここでviewportの中身の書き方を暗記する必要はありません。
								
								
											<meta name="viewport" content="width=device-width, initial-scale=1.0">
								
								
								
					responsive.cssの読み込み
					
								stylesheet.cssにメディアクエリ用のCSSを記述しても問題ありませんが、
								整理しやすいように今回はCSSファイルを分割し、responsive.cssにメディアクエリ用のCSSを記述していきます。
								
								
								
					floatと親要素の高さ
					
								通常、親要素の高さは子要素を包む高さとなります。
								しかし、子要素が全てfloatの時、親要素の高さは0となってしまうという性質があります。
								これは、floatは「浮いている」という意味で、親要素から見るとfloatの子要素は存在しないように見えるからです。
								
								
								
					floatの解除
					
								子要素が全てfloatでも、親要素が高さを持つように設定してみましょう。
								floatはclear: left;で「浮いている」状態を解除できます。
								ここではclear: left;を適用するためだけの空のタグを用意しましょう。
								空タグとclearでfloatを解除するのはよく使うテクニックなので、覚えておくようにしましょう。
								
								
								～.html
								
											  <div class = "clear">
            
         										 </div>
         									 
         									 
         							～.css
         						
         									.clear{
													  clear:left;
											}
											
											
											
					画面サイズが大きい時に対応しよう
					
								例えば2000pxの画面幅で表示すると、レッスン部分がお互いに離れすぎていて、見づらくなっています。これを直しましょう。
								
								container要素のwidthが100%なので、画面幅が2000pxなどとても大きい時も画面いっぱいに広がってしまいます。
								max-width: ◯◯px;と指定すると、画面幅を拡大しても、要素の幅の上限が◯◯pxとなります。
								
								
											.container {
														  max-width: 1170px;
														  width: 100%;
											}							
								
								
								
					要素の表示/非表示
								
								メニューアイコンはデフォルトでは非表示にし、画面幅が670px以下（スマートフォンサイズ）の時にのみ表示されるようにします。
								要素を非表示にするにはdisplay: none;を用います。
								非表示にした要素を表示させる時は、display: block;を用いて表示します。
								
								
								index.html
								
											 /* スマホ用のメニューアイコンを使用するための宣言 */
												<span class="fa fa-bars menu-icon"></span>
								
								
								
								stylesheet.css
								
												.menu-icon {
															  color: white;
															  float: right;
															  font-size: 25px;
															  padding: 21px 0;
															  
															  /* スマホ用のメニューアイコンを非表示にしておく */
															  display:none;
												}
								
								
								
								responsive.css
								
												/* スマホ向けレイアウト */
												@media all and (max-width: 670px) {
											
														/*スマホ用メニューに切り替えるので、デフォルトメニューを消す */
														  .header-right{
													  
																	display:none;
																
														  }
  
														  /* スマホ用メニューを表示  */
														  .menu-icon{
														  
																	 display:block;
																 
														  }
											}
											
										
										
					同名クラスを個別に指定
					
												 .top-wrapper  .btn{
												 
																  width:100%;
												}
												
												
												上記の書き方をすれば、top-wrapperクラスのbtnクラスだけがwidthが100%になる。
												
												
							
												
・Flexboxを学ぼう

			CSSを使ったレイアウト方法の1つであるFlexboxを学んでいきましょう。
			今まではfloatで作っていた横並びを、もっと簡単に作れるようになる。
			
			
					要素を横並びにする
					
											display: flexは指定した要素の子要素を横並びにします。
											横並びにしたい要素の親要素にdisplay: flexを指定します。
										
										
														～.html
														
															    <ul class="flex-list">
															      <li class="li1">item1</li>
															      <li class="li2">item2</li>
															      <li class="li3">item3</li>
															      <li class="li4">item4</li>
															    </ul>
															    
															    
														～．css
														
																.flex-list{
														
																 		display: flex
																	  
																}
																
																													
																
					要素の幅を伸縮させる
					
											flex: autoは指定した要素の幅を親要素に合わせて伸縮させることができます。
											親要素の幅に合わせて伸ばしたい要素にflex: autoを指定します。
											
											
														～.html
														
															    <ul class="flex-list">
															      <li class="li1">item1</li>
															      <li class="li2">item2</li>
															      <li class="li3">item3</li>
															      <li class="li4">item4</li>
															    </ul>
															    
															    
														～．css
														
																.flex-list{
														
																 		 flex:auto;
																	  
																}
																
																
					要素を折り返す
					
											flex-wrap: wrapを指定すると、子要素のサイズに応じて折り返すことができます。
											折り返したい要素の親要素にflex-wrap: wrapを指定します。
											折り返したい要素自身には列数に応じたwidthを指定します。
											今回は2列にしたいのでwidth: 50%を指定しましょう。
											
											
														～.html
														
															    <ul class="flex-list">
															      <li class="li1">item1</li>
															      <li class="li2">item2</li>
															      <li class="li3">item3</li>
															      <li class="li4">item4</li>
															    </ul>
															    
															    
														～．css
														
																.flex-list{
														
																 		display: flex;
																 		flex-wrap: wrap;
																	  
																}
																
																.flex-list li {
																
																		  flex: auto;
																		  width:50%;
  
																}
																
																
														※@media (max-width:1000px)でメディアクエリを設定すれば，スマホやタブレット表示にしたときに２列に折り返すことができる
					
					
					要素を1列に並べる
											flex-direction: columnは子要素を上から下へ並べます。
											縦に並べたい要素の親要素にflex-direction: columnを指定します。
											
											
																.flex-list{
														
																 		flex-direction: column;
																	  
																}
																
																.flex-list li {
																
																		  margin:0 auto;
  
																}
