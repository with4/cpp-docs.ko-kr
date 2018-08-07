---
title: 'Module:: unregistercomobject 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c19e7b5388438b8c3c2359672360e4a2ee3001a3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602632"
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
  
### <a name="parameters"></a>매개 변수  
 *서버 이름*  
 (사용되지 않음)  
  
 *쿠키*  
 등록 취소한 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 배열에서 만든 합니다 [RegisterCOMObject](../windows/module-registercomobject-method.md) 메서드.  
  
 *count*  
 등록 취소할 클래스 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 작업에 성공하면 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 HRESULT 오류가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [Module 클래스](../windows/module-class.md)