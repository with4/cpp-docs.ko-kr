---
title: "Module:: unregistercomobject 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45a6dc776feb1534cd7e58240a40cc173e7459de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="moduleunregistercomobject-method"></a>Module::UnregisterCOMObject 메서드
다른 응용 프로그램에서 COM 개체에 연결할 수 없도록 하나 이상의 COM 개체의 등록을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
#### <a name="parameters"></a>매개 변수  
 `serverName`  
 (사용되지 않음)  
  
 `cookies`  
 등록 취소한 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 배열에서 생성 된 [RegisterCOMObject](../windows/module-registercomobject-method.md) 메서드.  
  
 `count`  
 등록 취소할 클래스 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 작업에 성공하면 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 HRESULT 오류가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)