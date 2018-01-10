---
title: "책갈피를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 41c8e5a44130eebfddc9e99ab7ef815b6e8e43a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-bookmarks"></a>책갈피 사용
행 집합을 열기 전에 알려야 공급자 책갈피를 사용 하려면. 이 위해 설정 된 **DBPROP_BOOKMARKS** 속성을 **true** 속성을 설정 합니다. 공급자는 특수 매크로 사용 해야 열 0으로 책갈피를 검색 `BOOKMARK_ENTRY` 및 `CBookmark` 정적 접근자를 사용 하는 경우 클래스입니다. `CBookmark`책갈피 버퍼의 바이트 길이 인수가 있는 템플릿 클래스가입니다. 책갈피에 필요한 버퍼의 길이 공급자에 따라 달라 집니다. 다음 예제에 표시 된 대로 ODBC OLE DB 공급자를 사용 하는, 버퍼 4 바이트를 이어야 합니다.  
  
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
  
 사용 하는 경우 `CDynamicAccessor`, 버퍼를 런타임 시 동적으로 할당 됩니다. 이 경우의 특수 버전을 사용할 수는 있습니다 `CBookmark` 버퍼 길이 지정 하지 않습니다. 함수를 사용 하 여 `GetBookmark` 이 코드 예제에 나와 있는 것 처럼 현재 레코드에서 책갈피를 검색 하려면:  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
product.Open(session, "Products", &propset);  
product.MoveNext();  
product.GetBookmark(&bookmark);  
```  
  
 공급자의 책갈피 지원에 대 한 정보를 참조 하십시오. [공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)