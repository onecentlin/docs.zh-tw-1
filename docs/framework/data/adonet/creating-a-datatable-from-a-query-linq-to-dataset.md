---
title: "從查詢中建立 DataTable (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b97afeb-03f8-41e2-8eb3-58aff65f7d18
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 從查詢中建立 DataTable (LINQ to DataSet)
資料繫結 \(Data Binding\) 是 <xref:System.Data.DataTable> 物件的常見用法。  <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法會採用查詢的結果並將資料複製到 <xref:System.Data.DataTable> 中，然後此物件便可用於資料繫結。  執行了資料作業之後，新的 <xref:System.Data.DataTable> 就會合併回來源 <xref:System.Data.DataTable> 中。  
  
 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法會使用下列程序，從查詢中建立 <xref:System.Data.DataTable>：  
  
1.  <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法會從來源資料表 \(實作 <xref:System.Linq.IQueryable%601> 介面的 <xref:System.Data.DataTable> 物件\) 中複製 \(Clone\) <xref:System.Data.DataTable>。  <xref:System.Collections.IEnumerable> 來源通常源自於 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 運算式或方法查詢。  
  
2.  複製的 <xref:System.Data.DataTable> 結構描述是根據來源資料表中第一個列舉 <xref:System.Data.DataRow> 物件的資料行所建立，而且複製之資料表的名稱就是來源資料表的名稱並附加上 "query" 一字。  
  
3.  若為來源資料表中的每個資料列，資料列的內容會複製到新的 <xref:System.Data.DataRow> 物件中，然後該物件便插入複製的資料表中。  在複製作業中，<xref:System.Data.DataRow.RowState%2A> 和 <xref:System.Data.DataRow.RowError%2A> 屬性會保留下來。  如果來源中的 <xref:System.Data.DataRow> 物件來自於不同的資料表，系統就會擲回 <xref:System.ArgumentException>。  
  
4.  在輸入可查詢資料表中的所有 <xref:System.Data.DataRow> 物件都已經複製之後，就會傳回複製的 <xref:System.Data.DataTable>。  如果來源序列 \(Sequence\) 沒有包含任何 <xref:System.Data.DataRow> 物件，此方法就會傳回空的 <xref:System.Data.DataTable>。  
  
 請注意，呼叫 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法將導致系統執行繫結至來源資料表的查詢。  
  
 當 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法在來源資料表的資料列中遇到 Null 參考或可為 Null 的實值型別 \(Value Type\) 時，它會將此值取代成 <xref:System.DBNull.Value>。  如此一來，傳回之 <xref:System.Data.DataTable> 中的 Null 值都會經過正確處理。  
  
 注意：<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法會接受可從多個 <xref:System.Data.DataTable> 或 <xref:System.Data.DataSet> 物件傳回資料列的查詢當做輸入。  <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法會將資料 \(但不包含屬性\) 從來源 <xref:System.Data.DataTable> 或 <xref:System.Data.DataSet> 物件複製到傳回的 <xref:System.Data.DataTable>。  您必須針對傳回的 <xref:System.Data.DataTable> 明確設定屬性，例如 <xref:System.Data.DataTable.Locale%2A> 和 <xref:System.Data.DataTable.TableName%2A>。  
  
 下列範例將在 SalesOrderHeader 資料表中查詢是否有 2001 年 8 月 8 日之後的訂單，然後使用 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法，從該查詢中建立 <xref:System.Data.DataTable>。  接著，<xref:System.Data.DataTable> 便繫結至 <xref:System.Windows.Forms.BindingSource>，而它會當做 <xref:System.Windows.Forms.DataGridView> 的 Proxy。  
  
 [!code-csharp[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#copytodatatable1)]
 [!code-vb[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#copytodatatable1)]  
  
## 建立自訂 CopyToDataTable\<T\> 方法  
 現有的 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法只能在通用參數 `T` 為 <xref:System.Data.DataRow> 型別的<xref:System.Collections.Generic.IEnumerable%601> 來源上運作。  雖然這樣非常有用，但是資料表卻無法從一序列的純量型別、傳回匿名型別的查詢或執行資料表聯結的查詢建立。  如需如何實作從一序列的純量型別或匿名型別載入資料表的兩個自訂 `CopyToDataTable` 方法的範例，請參閱 [HOW TO：實作通用型別 T 不是 DataRow 的 CopyToDataTable\<T\>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)。  
  
 本節的範例都使用以下自訂型別：  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#itemclass)]
 [!code-vb[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#itemclass)]  
  
### 範例  
 此範例會執行 `SalesOrderHeader` 和 `SalesOrderDetail` 資料表的聯結，以取得八月的線上訂單資訊並根據此查詢建立資料表。  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#join)]
 [!code-vb[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#join)]  
  
### 範例  
 下列範例會查詢集合中價格大於 $9.99 的項目，並根據查詢結果建立資料表。  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintotable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintotable)]  
  
### 範例  
 下列範例會查詢集合中價格大於 $9.99 的項目並擲回結果。  所傳回的匿名型別序列就會載入到現有的資料表中。  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintoexistingtable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintoexistingtable)]  
  
### 範例  
 下列範例會查詢集合中價格大於 $9.99 的項目並擲回結果。  所傳回的匿名型別序列就會載入到現有的資料表中。  因為 `Book` 和 `Movies` 型別是衍生自 `Item` 型別，所以資料表結構描述會自動展開。  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsexpandschema)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsexpandschema)]  
  
### 範例  
 下列範例會查詢集合中價格大於 $9.99 的項目並傳回結果 <xref:System.Double> 序列，這序列會在入到新資料表中。  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loadscalarsequence)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loadscalarsequence)]  
  
## 請參閱  
 [程式設計手冊](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)   
 [泛型 Field 和 SetField 方法](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)   
 [LINQ to DataSet 範例](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)