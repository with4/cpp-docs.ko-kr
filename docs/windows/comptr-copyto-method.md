---
title: "Comptr:: Copyto 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::CopyTo
dev_langs: C++
helpviewer_keywords: CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f47df584fb456c721c92823a87ca525beb052d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrcopyto-method"></a>ComPtr::CopyTo 메서드
지정된 된 포인터를이 ComPtr과 연결 된 현재 또는 지정 된 인터페이스를 복사 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `U`  
 형식 이름.  
  
 `ptr`  
 이 작업이 완료 되 면 요청된 된 인터페이스에 대 한 포인터입니다.  
  
 `riid`  
 인터페이스 ID입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않은 경우 암시적 QueryInterface 작업이 실패 한 이유를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 함수는이 ComPtr과 연결 된 인터페이스에 대 한 포인터의 복사본을 반환 합니다. 이 함수는 항상 S_OK를 반환합니다.  
  
 으로 지정한 인터페이스에 대 한이 ComPtr과 연결 된 인터페이스에 QueryInterface 연산을 수행 하는 두 번째 함수는 `riid` 매개 변수입니다.  
  
 기본 인터페이스에 대 한이 ComPtr과 연결 된 인터페이스에 QueryInterface 연산을 수행 하는 세 번째 함수는 `U` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)