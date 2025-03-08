# DB構造定義

### メタデータ構造（SQL保存）

- member表
    -  name         : 名前（string）
    -  id           : アルファベットのみのID（string）
    -  description  : 自己紹介の短い文章（string）
    -  group        : 所属しているグループIDの配列（string[]）
    -  articles     : 執筆した記事のIDの配列（number[]）

- group表
    - name          : 名前（string）
    - id            : アルファベットのみのID（string）
    - description   : 紹介用の短い文章（string）
    - articles      : 執筆した記事のIDの配列（string[]）

- article表
    - id            : ID（string）
    - editor        : 執筆者のID（string）
    - title         : タイトル（string）
    - ogpImage      : OGP画像兼記事のトップに掲載する画像の仮想DBパス（string）

- contest表
    - id            : ID（string）
    - name          : 名前（string）
    - ogpImage      : OGP画像兼記事のトップに掲載する画像の仮想DBパス（string）

- image表
    - id            : ID（string）



### 動的データ構造（Git保存）

- :/blog
    - :/blog/[Member.name]      : メンバーのトップページ
        - :/blog/[Member.name]/[Article.id].md : メンバー固有記事のページ
    - :/blog/[Group.name].md       : 班のトップページ
        - :/blog/[Group.name]/[Article.id].md :班固有記事のページ
- :/contest
    - :/contest/[Contest.id].md    :コンテスト固有のページ
- :/image
    - :/image/[imageId].png/jpeg/webp/gif
