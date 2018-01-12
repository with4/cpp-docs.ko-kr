---
title: "BLOB 검색 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36ffc4fca7859b49067517e1085e1d854f733e24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="retrieving-a-blob"></a>BLOB 검색
다양 한 방법으로 binary large object (BLOB)을 검색할 수 있습니다. 사용할 수 있습니다 **DBTYPE_BYTES** 바이트의 시퀀스로 BLOB를 검색 하거나 같은 인터페이스를 사용 하 여 `ISequentialStream`합니다. 자세한 내용은 참조 [and OLE](https://msdn.microsoft.com/en-us/library/ms711511.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 다음 코드를 사용 하 여 BLOB를 검색 하는 방법을 보여 줍니다 `ISequentialStream`합니다. 매크로 [BLOB_ENTRY](../../data/oledb/blob-entry.md) 인터페이스와 인터페이스에 대해 사용 되는 플래그를 지정할 수 있습니다. 테이블을 연 후 코드에서 호출 **읽기** 에 반복 해 서 `ISequentialStream` BLOB에서 바이트를 읽을 수 있습니다. 코드를 호출 하 여 **릴리스** 호출 하기 전에 인터페이스 포인터를 삭제 하기 위해 `MoveNext` 다음 레코드를 가져올 수 있습니다.  
  
```  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories> > categories;  
ULONG          cb;  
BYTE            myBuffer[65536];  
  
categories.Open(session, "Categories");  
while (categories.MoveNext() == S_OK)  
{  
   do  
   {  
      categories.pPicture->Read(myBuffer, 65536, &cb);  
      // Do something with the buffer  
   } while (cb > 0);  
   categories.pPicture->Release();  
}  
```  
  
 BLOB 데이터를 처리 하는 매크로 대 한 자세한 내용은의 "열 맵 매크로" 참조 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)   
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)