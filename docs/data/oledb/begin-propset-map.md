---
title: BEGIN_PROPSET_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROPSET_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_PROPSET_MAP macro
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 24fe8ed41888ab2b3d303a29cd9d004f26b6c6b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="beginpropsetmap"></a>BEGIN_PROPSET_MAP
표시 된 속성의 시작 부분 맵 항목을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
BEGIN_PROPSET_MAP(  
Class   
)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 *클래스*  
 [in] 이 속성 집합이 지정 된 클래스입니다. 다음 OLE DB 개체의 속성 집합을 지정할 수 있습니다.  
  
-   [데이터 원본 개체](https://msdn.microsoft.com/en-us/library/ms721278.aspx)  
  
-   [세션 개체](https://msdn.microsoft.com/en-us/library/ms711572.aspx)  
  
-   [명령](https://msdn.microsoft.com/en-us/library/ms724608.aspx)  
  
## <a name="example"></a>예  
 샘플 속성 집합 맵에 다음과 같습니다.  
  
 [!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)