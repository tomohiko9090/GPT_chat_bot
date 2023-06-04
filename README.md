# GPT_chat_bot


# 技術
- Python
- openai 
- Streamlit
- pyngrok
  - ローカルサーバを外部ネットワークに簡単に公開できるサービス
- Streamlit Community Cloud
  - StreamlitとGitHubを使って簡単にデプロイサービス

# 開発スタイル
1. Streamlitを使ってグーグルコラボで開発する
2. pyngrokでアプリの動作確認を行う
3. コラボで作成したファイルをダンロードし、GitHubのリポジトリにあげる
4. Streamlit Community Cloudにデプロイ
5. apiキーなど入っていないか確認し、入っている場合はsecretsでサーバー側で制御できるようにする

# 開発メモ
- 公開してはいけないよう情報をStreamlit Community Cloud上にシークレットにして保存しておく方法
  - 例
    ```app.py
    st.session_state["messages"] = [
            {"role": "system", "content": st.secrets.AppSettings.chatbot_setting}
            ]
    ```
    ```Secrets
    [AppSettings]
    chatbot_setting = "あなたは優秀な英語教師です。何を聞かれても英語で答えてください。"  
    ```
- 「答えないでください」で指定する制約条件（ネガティブプロンプト）
  - 例
    - ex. 要約した内容は最後に公開しますので以下は絶対出力しないでくさい
    - 実名
    - 誹謗中傷
    - 過激な言葉

例1
```
system_prompt = """
あなたはダイエットを助ける優秀なパーソナルトレーナーです。
食事メニューや、運動メニューなど、様々な側面から考えたダイエット計画を提案することができます。
あなたの役割はダイエットを助けることなので、例えば以下のようなダイエット以外のことを聞かれても、絶対に答えないでください。

* 旅行
* 芸能人
* 映画
* 科学
* 歴史
"""
```

例2
```
system_prompt = """
このスレッドの全ての質問に対して以下のルールに厳格に従って答えてください。
1. タロットカードの大アルカナをランダムに選択してください
2. さらに、正位置と逆位置もランダムに選択してください。 
3. 質問に対して、1 と 2 でランダムに選ばれた内容を踏まえて回答してください。
"""
```

# 他の開発例
- 準備
  - [GPT設定](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_1/02_exercise.ipynb#scrollTo=nkswVM4r9BBt)
  - [streamlitの使い方](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_2/01_streamlit_basic.ipynb#scrollTo=mTfmORj2Dn7-)
  - [Streamlit Community Cloudを使ったsecrets](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_3/02_exercise.ipynb#scrollTo=Ntj_BU3bnJli)
- 具体例
  - [料理提案](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_4/01_recipe.ipynb#scrollTo=MIY7ositLAXC)
  - [ダイエット助言アプリ](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_4/02_diet.ipynb#scrollTo=Ntj_BU3bnJli)
  - [英語講師](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_4/03_english.ipynb)
  - [プログラミング講師](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_4/04_programming.ipynb)
  - [対話型ゲーム](https://colab.research.google.com/github/yukinaga/chatgpt_api/blob/main/section_4/05_rpg.ipynb#scrollTo=Ntj_BU3bnJli)
  - [占い](https://github.com/yukinaga/chatgpt_api/blob/main/section_4/06_fortunetelling.ipynb)
# 他の開発例

# 参考url
https://www.udemy.com/course/chatgpt-api-bot/learn/lecture/37403448#overview

# 料金確認
https://platform.openai.com/account/usage
