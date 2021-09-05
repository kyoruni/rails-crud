# README

## テーブル設計（ WIP ）

### pokemons ポケモン

| Column  | Type       | Options | Comment |
| :----:  | :----:     | :----:  | :----: |
| id      | INT        | UNSIGNED, NOT NULL, AUTO_INCREMENT | ID |
| name    | VARCHAR(6) | NOT NULL           | 名前 |
| no      | INT        | UNSIGNED, NOT NULL | 図鑑ナンバー |
| species | VARCHAR(25)| NOT NULL           | ぶんるい |
| height  | INT        | UNSIGNED, NOT NULL | たかさ |
| weight  | INT        | UNSIGNED, NOT NULL | おもさ |

### types タイプ

| Column | Type       | Options | Comment |
| :----: | :----:     | :----:  | :----:  |
| id     | INT        | UNSIGNED, NOT NULL, AUTO_INCREMENT | ID |
| name   | VARCHAR(5) | NOT NULL | 名前 |

### pokemon_types ポケモン_タイプ

| Column     | Type   | Options | Comment |
| :----:     | :----: | :----: | :----: |
| id         | INT    | UNSIGNED, NOT NULL, AUTO_INCREMENT | ID |
| pokemon_id | INT    | UNSIGNED, NOT NULL, AUTO_INCREMENT | ポケモンID |
| type_id    | INT    | UNSIGNED, NOT NULL, AUTO_INCREMENT | タイプID |

### skills わざ

| Column   | Type        | Options | Comment |
| :----:   | :----:      | :----:  | :----: |
| id       | INT         | UNSIGNED, NOT NULL, AUTO_INCREMENT | ID |
| name     | VARCHAR(50) | NOT NULL | 名前 |
| type_id  | INT         | UNSIGNED, NOT NULL | タイプID |
| power    | INT         | UNSIGNED | 威力(変化技の場合があるので、null許可) |
| accuracy | INT         | UNSIGNED, NOT NULL | 命中率 |
| category_id | INT         | UNSIGNED, NOT NULL | 分類ID |

##### skills_category 技の分類

| Column   | Type        | Options | Comment |
| :----:   | :----:      | :----:  | :----: |
| id       | INT         | UNSIGNED, NOT NULL, AUTO_INCREMENT | ID |
| name     | VARCHAR(50) | NOT NULL | 名前 |

| id | name |
| :----: | :----: |
| 1 | 物理 physical |
| 2 | 特殊 special |
| 3 | 変化 status |

### pokemon_skills ポケモン_わざ

| Column     | Type   | Options | Comment |
| :----:     | :----: | :----:  | :----: |
| id         | INT    | UNSIGNED, NOT NULL, AUTO_INCREMENT | ID |
| pokemon_id | INT    | UNSIGNED, NOT NULL | ポケモンID |
| skill_id   | INT    | UNSIGNED, NOT NULL | わざID |