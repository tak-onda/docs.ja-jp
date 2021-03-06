---
title: SQL Server スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: c6403cc3-d78b-4f85-bab1-ada7a3446ec5
ms.openlocfilehash: 2445ab2ffbe30b647e256e223f712300bcf19931
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635040"
---
# <a name="sql-server-schema-collections"></a>SQL Server スキーマ コレクション
Microsoft .NET Framework Data Provider for SQL Server は、共通のスキーマ コレクションに加えて追加のスキーマ コレクションをサポートしています。 スキーマ コレクションは、使用している SQL Server のバージョンによって多少異なります。 サポートされるスキーマ コレクションの一覧を確認するのには、呼び出し、 **GetSchema**メソッド引数なしでまたはスキーマ コレクション名に"metadatacollections を指定"します。 これにより、サポートされるスキーマ コレクションの一覧、それぞれがサポートする制限数、および使用する識別子部分の数と共に、<xref:System.Data.DataTable> が返されます。  
  
## <a name="databases"></a>Databases  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|database_name|String|データベース名。|  
|dbid|Int16|データベース ID。|  
|create_date|DateTime|データベースの作成日。|  
  
## <a name="foreign-keys"></a>Foreign Keys  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|CONSTRAINT_CATALOG|String|制約が属するカタログ。|  
|CONSTRAINT_SCHEMA|String|制約を含むスキーマ。|  
|CONSTRAINT_NAME|String|名前。|  
|TABLE_CATALOG|String|制約が含まれるテーブル名。|  
|TABLE_SCHEMA|String|テーブルを含むスキーマ。|  
|TABLE_NAME|String|テーブル名|  
|CONSTRAINT_TYPE|String|制約の型。 "FOREIGN KEY" だけが許可されています。|  
|IS_DEFERRABLE|String|制約を遅延可能にするかどうかを指定します。 NO が返されます。|  
|INITIALLY_DEFERRED|String|制約を最初に遅延可能にするかどうかを指定します。 NO が返されます。|  
  
## <a name="indexes"></a>Indexes  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|constraint_catalog|String|インデックスが属するカタログ。|  
|constraint_schema|String|インデックスを含むスキーマ。|  
|constraint_name|String|インデックス名。|  
|table_catalog|String|インデックスが関連付けられているテーブル名。|  
|table_schema|String|インデックスが関連付けられているテーブルを含むスキーマ。|  
|table_name|String|テーブル名。|  
|index_name|String|インデックスの名前。|  
  
### <a name="indexes-sql-server-2008"></a>Indexes (SQL Server 2008)  
 .NET Framework 3.5 SP1 および SQL Server 2008 以降では、新しい空間型、ファイルストリーム、およびスパース列をサポートするために、以下の列が Indexes スキーマ コレクションに追加されています。 これらの列は、以前のバージョンの .NET Framework および SQL Server ではサポートされません。  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|type_desc|String|インデックスの種類。次のいずれかの値になります。<br /><br /> -ヒープ<br />クラスター化<br />-   NONCLUSTERED<br />-   XML<br />空間|  
  
## <a name="indexcolumns"></a>IndexColumns  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|constraint_catalog|String|インデックスが属するカタログ。|  
|constraint_schema|String|インデックスを含むスキーマ。|  
|constraint_name|String|インデックス名。|  
|table_catalog|String|インデックスが関連付けられているテーブル名。|  
|table_schema|String|インデックスが関連付けられているテーブルを含むスキーマ。|  
|table_name|String|テーブル名。|  
|column_name|String|インデックスが関連付けられている列名。|  
|ordinal_position|Int32|列の位置を示す序数。|  
|KeyType|Byte|オブジェクトの型。|  
|index_name|String|インデックスの名前。|  
  
## <a name="procedures"></a>手順  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|String|カタログ固有の名前。|  
|SPECIFIC_SCHEMA|String|スキーマ固有の名前。|  
|SPECIFIC_NAME|String|カタログ固有の名前。|  
|ROUTINE_CATALOG|String|ストアド プロシージャが属するカタログ。|  
|ROUTINE_SCHEMA|String|ストアド プロシージャを含むスキーマ。|  
|ROUTINE_NAME|String|ストアド プロシージャの名前。|  
|ROUTINE_TYPE|String|ストアド プロシージャには PROCEDURE が返され、関数には FUNCTION が返されます。|  
|CREATED|DateTime|プロシージャが作成された日時。|  
|LAST_ALTERED|DateTime|プロシージャの最終更新日時。|  
  
## <a name="procedure-parameters"></a>Procedure Parameters  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|String|このパラメーターを受け取るプロシージャのカタログ名。|  
|SPECIFIC_SCHEMA|String|このパラメーターを受け取るプロシージャを含むスキーマ。|  
|SPECIFIC_NAME|String|このパラメーターを受け取るとるプロシージャ名。|  
|ORDINAL_POSITION|Int32|パラメーターの位置を示す 1 から始まる序数。 プロシージャの戻り値については 0 になります。|  
|PARAMETER_MODE|String|入力パラメーターでは IN が返され、出力パラメーターでは OUT が返され、I/O パラメーターでは INOUT が返されます。|  
|IS_RESULT|String|プロシージャの結果が関数を表す場合には YES が返されます。 その他の場合は NO が返されます。|  
|AS_LOCATOR|String|ロケーターとして宣言された場合は YES が返されます。 その他の場合は NO が返されます。|  
|PARAMETER_NAME|String|パラメーターの名前。 関数の戻り値に相当する場合は NULL になります。|  
|DATA_TYPE|String|システムにより提供されるデータ型。|  
|CHARACTER_MAXIMUM_LENGTH|Int32|バイナリまたは文字データ型の文字列の最大長。 その他の場合は NULL が返されます。|  
|CHARACTER_OCTET_LENGTH|Int32|バイナリまたは文字データ型の最大バイト数。 その他の場合は NULL が返されます。|  
|COLLATION_CATALOG|String|パラメーター照合のカタログ名。 文字型の 1 つでない場合は、NULL が返されます。|  
|COLLATION_SCHEMA|String|常に NULL が返されます。|  
|COLLATION_NAME|String|パラメーター照合の名前。 文字型の 1 つでない場合は、NULL が返されます。|  
|CHARACTER_SET_CATALOG|String|パラメーターの文字セットのカタログ名。 文字型の 1 つでない場合は、NULL が返されます。|  
|CHARACTER_SET_SCHEMA|String|常に NULL が返されます。|  
|CHARACTER_SET_NAME|String|パラメーターの文字セット名。 文字型の 1 つでない場合は、NULL が返されます。|  
|NUMERIC_PRECISION|Byte|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数。 その他の場合は NULL が返されます。|  
|NUMERIC_PRECISION_RADIX|Int16|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数の基数。 その他の場合は NULL が返されます。|  
|NUMERIC_SCALE|Int32|数値データの概数、正確な数値データ、整数データ、または通貨データの桁数。 その他の場合は NULL が返されます。|  
|DATETIME_PRECISION|Int16|パラメーターの型が datetime または smalldatetime である場合の秒数の小数部の有効桁数。 その他の場合は NULL が返されます。|  
|INTERVAL_TYPE|String|NULL。 将来 SQL Server で使用するために予約されています。|  
|INTERVAL_PRECISION|Int16|NULL。 将来 SQL Server で使用するために予約されています。|  
  
## <a name="tables"></a>[テーブル]  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|テーブルのカタログ。|  
|TABLE_SCHEMA|String|テーブルを含むスキーマ。|  
|TABLE_NAME|String|テーブル名。|  
|TABLE_TYPE|String|テーブルの型。 VIEW または BASE TABLE のいずれかです。|  
  
## <a name="columns"></a>列  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|テーブルのカタログ。|  
|TABLE_SCHEMA|String|テーブルを含むスキーマ。|  
|TABLE_NAME|String|テーブル名。|  
|COLUMN_NAME|String|列名。|  
|ORDINAL_POSITION|Int32|列の識別番号。|  
|COLUMN_DEFAULT|String|列の既定値。|  
|IS_NULLABLE|String|列に NULL 値が許容されるかどうかを指定します。 この列に NULL が許容される場合は、YES が返されます。 その他の場合は NO が返されます。|  
|DATA_TYPE|String|システムにより提供されるデータ型。|  
|CHARACTER_MAXIMUM_LENGTH|Int32 – Sql8、Int16 – Sql7|バイナリ データ、文字データ、またはテキストおよびイメージ データの最大文字列長。 その他の場合は NULL が返されます。|  
|CHARACTER_OCTET_LENGTH|Int32 – SQL8、Int16 – Sql7|バイナリ データ、文字データ、またはテキストおよびイメージ データの最大バイト長。 その他の場合は NULL が返されます。|  
|NUMERIC_PRECISION|Unsigned Byte|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数。 その他の場合は NULL が返されます。|  
|NUMERIC_PRECISION_RADIX|Int16|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数の基数。 その他の場合は NULL が返されます。|  
|NUMERIC_SCALE|Int32|数値データの概数、正確な数値データ、整数データ、または通貨データの桁数。 その他の場合は NULL が返されます。|  
|DATETIME_PRECISION|Int16|日付時刻データ型および SQL-92 interval データ型のサブタイプ コード。 その他のデータ型に対しては NULL が返されます。|  
|CHARACTER_SET_CATALOG|String|列が文字データ型またはテキスト データ型である場合は、文字セットがあるデータベースを示すマスターが返されます。 その他の場合は NULL が返されます。|  
|CHARACTER_SET_SCHEMA|String|常に NULL が返されます。|  
|CHARACTER_SET_NAME|String|この列が文字データ型またはテキスト データ型である場合、文字セットの一意の名前が返されます。 その他の場合は NULL が返されます。|  
|COLLATION_CATALOG|String|列が文字データ型またはテキスト データ型である場合は、照合順序が定義されているデータベースを示すマスターが返されます。 その他の場合、この列は NULL になります。|  
  
### <a name="columns-sql-server-2008"></a>Columns (SQL Server 2008)  
 .NET Framework version 3.5 SP1 および SQL Server 2008 以降では、新しい空間型、filestream、およびスパース列をサポートするために、以下の列が Columns スキーマ コレクションに追加されています。 これらの列は、以前のバージョンの .NET Framework および SQL Server ではサポートされません。  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|IS_FILESTREAM|String|列に FILESTREAM 属性がある場合は YES。<br /><br /> 列には FILESTREAM 属性がない場合は NO。|  
|IS_SPARSE|String|列がスパース列である場合は YES。<br /><br /> 列がスパース列でない場合は NO。|  
|IS_COLUMN_SET|String|列が列セットの列である場合は YES。<br /><br /> 列が列セットの列でない場合は NO。|  
  
### <a name="allcolumns-sql-server-2008"></a>AllColumns (SQL Server 2008)  
 .NET Framework version 3.5 SP1 および SQL Server 2008 以降では、スパース列をサポートするために、AllColumns スキーマ コレクションが追加されています。 AllColumns は、以前のバージョンの .NET Framework および SQL Server ではサポートされません。  
  
 AllColumns の制限と生成される DataTable スキーマは、Columns スキーマ コレクションと同じです。 相違は、Columns スキーマ コレクションに含まれていない列セットの列が AllColumns に含まれている点のみです。 次の表では、それらの列について説明します。  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|テーブルのカタログ。|  
|TABLE_SCHEMA|String|テーブルを含むスキーマ。|  
|TABLE_NAME|String|テーブル名。|  
|COLUMN_NAME|String|列名。|  
|ORDINAL_POSITION|Int32|列の識別番号。|  
|COLUMN_DEFAULT|String|列の既定値。|  
|IS_NULLABLE|String|列に NULL 値が許容されるかどうかを指定します。 この列に NULL が許容される場合は、YES が返されます。 その他の場合は NO が返されます。|  
|DATA_TYPE|String|システムにより提供されるデータ型。|  
|CHARACTER_MAXIMUM_LENGTH|Int32|バイナリ データ、文字データ、またはテキストおよびイメージ データの最大文字列長。 その他の場合は NULL が返されます。|  
|CHARACTER_OCTET_LENGTH|Int32|バイナリ データ、文字データ、またはテキストおよびイメージ データの最大バイト長。 その他の場合は NULL が返されます。|  
|NUMERIC_PRECISION|Unsigned Byte|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数。 その他の場合は NULL が返されます。|  
|NUMERIC_PRECISION_RADIX|Int16|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数の基数。 その他の場合は NULL が返されます。|  
|NUMERIC_SCALE|Int32|数値データの概数、正確な数値データ、整数データ、または通貨データの桁数。 その他の場合は NULL が返されます。|  
|DATETIME_PRECISION|Int16|日付時刻データ型および SQL-92 interval データ型のサブタイプ コード。 その他のデータ型に対しては NULL が返されます。|  
|CHARACTER_SET_CATALOG|String|列が文字データ型またはテキスト データ型である場合は、文字セットがあるデータベースを示すマスターが返されます。 その他の場合は NULL が返されます。|  
|CHARACTER_SET_SCHEMA|String|常に NULL が返されます。|  
|CHARACTER_SET_NAME|String|この列が文字データ型またはテキスト データ型である場合、文字セットの一意の名前が返されます。 その他の場合は NULL が返されます。|  
|COLLATION_CATALOG|String|列が文字データ型またはテキスト データ型である場合は、照合順序が定義されているデータベースを示すマスターが返されます。 その他の場合、この列は NULL になります。|  
|IS_FILESTREAM|String|列に FILESTREAM 属性がある場合は YES。<br /><br /> 列には FILESTREAM 属性がない場合は NO。|  
|IS_SPARSE|String|列がスパース列である場合は YES。<br /><br /> 列がスパース列でない場合は NO。|  
|IS_COLUMN_SET|String|列が列セットの列である場合は YES。<br /><br /> 列が列セットの列でない場合は NO。|  
  
### <a name="columnsetcolumns-sql-server-2008"></a>ColumnSetColumns (SQL Server 2008)  
 .NET Framework version 3.5 SP1 および SQL Server 2008 以降では、スパース列をサポートするために、ColumnSetColumns スキーマ コレクションが追加されています。 ColumnSetColumns は、以前のバージョンの .NET Framework および SQL Server ではサポートされません。 ColumnSetColumns スキーマ コレクションは、列セット内のすべての列のスキーマを返します。 次の表では、それらの列について説明します。  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|テーブルのカタログ。|  
|TABLE_SCHEMA|String|テーブルを含むスキーマ。|  
|TABLE_NAME|String|テーブル名。|  
|COLUMN_NAME|String|列名。|  
|ORDINAL_POSITION|Int32|列の識別番号。|  
|COLUMN_DEFAULT|String|列の既定値。|  
|IS_NULLABLE|String|列に NULL 値が許容されるかどうかを指定します。 この列に NULL が許容される場合は、YES が返されます。 その他の場合は NO が返されます。|  
|DATA_TYPE|String|システムにより提供されるデータ型。|  
|CHARACTER_MAXIMUM_LENGTH|Int32|バイナリ データ、文字データ、またはテキストおよびイメージ データの最大文字列長。 その他の場合は NULL が返されます。|  
|CHARACTER_OCTET_LENGTH|Int32|バイナリ データ、文字データ、またはテキストおよびイメージ データの最大バイト長。 その他の場合は NULL が返されます。|  
|NUMERIC_PRECISION|Unsigned Byte|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数。 その他の場合は NULL が返されます。|  
|NUMERIC_PRECISION_RADIX|Int16|数値データの概数、正確な数値データ、整数データ、または通貨データの有効桁数の基数。 その他の場合は NULL が返されます。|  
|NUMERIC_SCALE|Int32|数値データの概数、正確な数値データ、整数データ、または通貨データの桁数。 その他の場合は NULL が返されます。|  
|DATETIME_PRECISION|Int16|日付時刻データ型および SQL-92 interval データ型のサブタイプ コード。 その他のデータ型に対しては NULL が返されます。|  
|CHARACTER_SET_CATALOG|String|列が文字データ型またはテキスト データ型である場合は、文字セットがあるデータベースを示すマスターが返されます。 その他の場合は NULL が返されます。|  
|CHARACTER_SET_SCHEMA|String|常に NULL が返されます。|  
|CHARACTER_SET_NAME|String|この列が文字データ型またはテキスト データ型である場合、文字セットの一意の名前が返されます。 その他の場合は NULL が返されます。|  
|COLLATION_CATALOG|String|列が文字データ型またはテキスト データ型である場合は、照合順序が定義されているデータベースを示すマスターが返されます。 その他の場合、この列は NULL になります。|  
|IS_FILESTREAM|String|列に FILESTREAM 属性がある場合は YES。<br /><br /> 列には FILESTREAM 属性がない場合は NO。|  
|IS_SPARSE|String|列がスパース列である場合は YES。<br /><br /> 列がスパース列でない場合は NO。|  
|IS_COLUMN_SET|String|列が列セットの列である場合は YES。<br /><br /> 列が列セットの列でない場合は NO。|  
  
## <a name="users"></a>Users  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|uid|Int16|このデータベースで一意のユーザー ID。 1 はデータベースの所有者です。|  
|user_name|String|このデータベースで一意のユーザー名またはグループ名。|  
|createdate|DateTime|アカウントが追加された日付。|  
|updatedate|DateTime|アカウントが最後に変更された日付。|  
  
## <a name="views"></a>ビュー  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|String|ビューのカタログ。|  
|TABLE_SCHEMA|String|ビューを含むスキーマ。|  
|TABLE_NAME|String|ビューの名前。|  
|CHECK_OPTION|String|WITH CHECK OPTION の型。 元のビューが WITH CHECK OPTION を使用して作成されている場合は CASCADE になります。 その他の場合は NONE が返されます。|  
|IS_UPDATABLE|String|ビューが更新可能であるかどうかを指定します。 常に NO が返されます。|  
  
## <a name="viewcolumns"></a>ViewColumns  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|VIEW_CATALOG|String|ビューのカタログ。|  
|VIEW_SCHEMA|String|ビューを含むスキーマ。|  
|VIEW_NAME|String|ビューの名前。|  
|TABLE_CATALOG|String|このビューに関連付けられているテーブルのカタログ。|  
|TABLE_SCHEMA|String|このビューに関連付けられているテーブルを含むスキーマ。|  
|TABLE_NAME|String|ビューに関連付けられているテーブルの名前。 ベース テーブルになります。|  
|COLUMN_NAME|String|列名。|  
  
## <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|ColumnName|DataType|説明|  
|----------------|--------------|-----------------|  
|assembly_name|String|アセンブリのファイル名。|  
|udt_name|String|アセンブリのクラス名。|  
|version_major|Object|メジャー バージョン番号。|  
|version_minor|Object|マイナー バージョン番号。|  
|version_build|Object|ビルド番号。|  
|version_revision|Object|リビジョン番号。|  
|culture_info|Object|この UDT に関連付けられているカルチャ情報。|  
|public_key|Object|このアセンブリで使用される公開キー。|  
|is_fixed_length|ブール型|型の長さを max_length と常に同じにするかどうかを指定します。|  
|max_length|Int16|型の最大長 (バイト単位)。|  
|Create_Date|DateTime|アセンブリが作成/登録された日付。|  
|Permission_set_desc|String|アセンブリのアクセス許可セット/セキュリティ レベルのフレンドリ名。|  
  
## <a name="see-also"></a>関連項目
- [データベース スキーマ情報の取得](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター](https://go.microsoft.com/fwlink/?LinkId=217917)
