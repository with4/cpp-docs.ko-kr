---
title: "Classfactory:: Queryinterface 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: 9593881f-4585-4d70-8ca6-b328918d4d6b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c4abb408ded66f9768cd1e1476f131b3f82cd30
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="classfactoryqueryinterface-method"></a>ClassFactory::QueryInterface 메서드
매개 변수에 의해 지정 된 인터페이스에 대 한 포인터를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 인터페이스 ID입니다.  
  
 `ppvObject`  
 이 작업이 완료 될 때 매개 변수로 지정 된 인터페이스에 대 한 포인터 `riid`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ClassFactory 클래스](../windows/classfactory-class.md)