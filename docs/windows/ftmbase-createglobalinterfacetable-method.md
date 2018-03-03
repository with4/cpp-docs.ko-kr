---
title: "Ftmbase:: Createglobalinterfacetable 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs:
- C++
helpviewer_keywords:
- CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc96d8eaff3def90f9ff3e9bd76e0ef067094715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>FtmBase::CreateGlobalInterfaceTable 메서드
(GIT) 전역 인터페이스 테이블을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `git`  
 이 작업이 완료 될 때, 전역 인터페이스 테이블에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 MSDN Library에서 "COM 참조" 항목의 "COM 인터페이스" 하위 항목인 "IGlobalInterfaceTable" 항목을 참조 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)