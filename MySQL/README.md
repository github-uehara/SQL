### MySQL学習用リポジトリ

動作確認用テーブルの準備
```
-- 社員テーブル
CREATE TABLE tt_employee( 
    employee_id VARCHAR (4) NOT NULL
    , employee_nm VARCHAR (32) NOT NULL
    , position_cd VARCHAR (4) NOT NULL
    , join_date DATE NOT NULL
    , retire_flag VARCHAR (1) NOT NULL
    , PRIMARY KEY (employee_id)
    , FOREIGN KEY fk_position_cd(position_cd) REFERENCES tt_position(position_cd)
);
INSERT INTO tt_employee VALUES ('A001', '島根', 'J001', '2000/01/01', '0');
INSERT INTO tt_employee VALUES ('A002', '岡山', 'J001', '2000/02/01', '0');
INSERT INTO tt_employee VALUES ('A003', '新潟', 'J002', '2000/03/01', '0');
INSERT INTO tt_employee VALUES ('A004', '蝦夷地', 'E001', '1999/01/01', '1');
INSERT INTO tt_employee VALUES ('A005', '神奈川', 'M001', '2000/04/01', '0');
INSERT INTO tt_employee VALUES ('A006', '江戸', 'G999', '1999/01/01', '1');

-- 役職テーブル
CREATE TABLE tt_position( 
    position_cd VARCHAR (4) NOT NULL
    , position_nm VARCHAR (32) NOT NULL
    , PRIMARY KEY (position_cd)
);
INSERT INTO TT_POSITION VALUES ('J001', 'ジュニア1');
INSERT INTO TT_POSITION VALUES ('J002', 'ジュニア2');
INSERT INTO TT_POSITION VALUES ('A001', 'アソシエイト1');
INSERT INTO TT_POSITION VALUES ('E001', 'エンジニア1');
INSERT INTO TT_POSITION VALUES ('M001', 'マネージャー1');
INSERT INTO TT_POSITION VALUES ('G999', '社長');

```
