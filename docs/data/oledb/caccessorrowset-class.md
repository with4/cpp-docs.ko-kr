---
title: "CAccessorRowset 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
dev_langs: C++
helpviewer_keywords: CAccessorRowset class
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4b7340baabb24ef18806442504a4bd5dadf73a41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="caccessorrowset-class"></a>CAccessorRowset 클래스
행 집합 및 해당 관련된 접근자 단일 클래스에 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CAccessorRowset :   
   public TAccessor,    
   public TRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TAccessor`  
 접근자 클래스입니다.  
  
 `TRowset`  
 행 집합 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[바인딩](../../data/oledb/caccessorrowset-bind.md)|바인딩을 만듭니다 (때 **bBind** 에서 false로 지정 된 [ccommand:: Open](../../data/oledb/ccommand-open.md)).|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|생성자입니다.|  
|[닫기](../../data/oledb/caccessorrowset-close.md)|접근자 및 행 집합을 닫습니다.|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|해제 해야 하는 현재 레코드의 모든 열을 해제 합니다.|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|구현 [icolumnsinfo:: Getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)합니다.|  
  
## <a name="remarks"></a>설명  
 클래스 `TAccessor` 접근자를 관리 합니다. 클래스 *TRowset* 행 집합을 관리 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)