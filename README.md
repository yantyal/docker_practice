# docker_practice

docker compose up -d  

DBにはmysqlを使用しています。mysqlのコンテナ起動後にテーブルを作成する必要があります。

-- ユーザー情報テーブル  
create table user_info (
  user_id INT not null auto_increment comment 'ユーザーID'
  , name VARCHAR(256) not null comment 'ユーザー名'
  , mail VARCHAR(256) not null comment 'メールアドレス'
  , password VARCHAR(256) not null comment 'パスワード'
  , constraint user_info_PKC primary key (user_id)
) ;

-- 投稿ユーザーテーブル  
create table post_user (
  post_user_id INT not null AUTO_INCREMENT comment '投稿ユーザーID'
  , post_id INT not null comment '投稿ID'
  , user_id INT not null comment 'ユーザーID'
  , delete_flag CHAR default '0' not null comment '削除フラグ'
  , constraint POST_USER_PKC primary key (post_user_id)
) ;

-- 投稿テーブル  
create table post (
  post_id INT not null AUTO_INCREMENT comment '投稿ID'
  , image_path VARCHAR(256) comment '画像パス'
  , post TEXT not null comment '投稿'
  , updated_at DATETIME not null comment '最終更新日時'
  , constraint POST_PKC primary key (post_id)
) ;



