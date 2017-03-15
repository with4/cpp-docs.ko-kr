---
title: "책갈피 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "책갈피, OLE DB"
  - "OLE DB 공급자 템플릿, 책갈피"
  - "OLE DB 공급자, 책갈피 지원"
  - "행 집합, 책갈피"
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 책갈피 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

행 집합을 열기 전에, 공급자에게 책갈피를 사용하려는 사실을 알려야 합니다.  이렇게 하려면 속성 설정에서 **DBPROP\_BOOKMARKS** 속성을 **true**로 설정하십시오.  공급자는 책갈피를 열 0으로 검색하므로 정적 접근자를 사용하는 경우에는 특수 매크로 `BOOKMARK_ENTRY` 및 `CBookmark` 클래스를 사용해야 합니다.  `CBookmark`는 책갈피 버퍼의 바이트 길이가 인수로 사용되는 템플릿 클래스입니다.  책갈피에 필요한 버퍼의 길이는 공급자에 따라 다릅니다.  ODBC OLE DB 공급자를 사용하고 있으면, 다음 예제에서처럼 버퍼가 4바이트이어야 합니다.  
  
```  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
  
CTable<CAccessor<CProducts> > product;  
product.Open(session, "Products", &propset);  
```  
  
 `CDynamicAccessor`를 사용하는 경우, 버퍼는 런타임에 동적으로 할당됩니다.  이 경우, 버퍼 길이를 지정하지 않는 `CBookmark`의 특수 버전을 사용할 수 있습니다.  다음 코드 예제에서처럼 함수 `GetBookmark`를 사용하여 현재 레코드의 책갈피를 검색할 수 있습니다.  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
product.Open(session, "Products", &propset);  
product.MoveNext();  
product.GetBookmark(&bookmark);  
```  
  
 공급자의 책갈피 지원에 대한 자세한 내용은 [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)을 참조하십시오.  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)