---
title: SafeCast | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeCast
dev_langs:
- C++
helpviewer_keywords:
- SafeCast function
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c3c9bb208cc2be2f91d8a464787d3299cd0b386
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="safecast"></a>SafeCast
한 가지 형식의 숫자를 다른 형식으로 캐스팅합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T, typename U>  
inline bool SafeCast (  
   const T From,  
   U& To  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `From`  
 변환할 원본 숫자입니다. T 형식이어야 합니다.  
  
 [out] `To`  
 새 숫자 형식에 대 한 참조입니다. U 형식이어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true`오류가 발생 하지 않으면; `false` 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는의 일부 [SafeInt 라이브러리](../windows/safeint-library.md) 용인지 단일 캐스팅 작업의 인스턴스를 만들지 않고 및는 [SafeInt 클래스](../windows/safeint-class.md)합니다.  
  
> [!NOTE]
>  이 메서드는 한 번의 작업을 보호 해야 하는 경우에 사용 해야 합니다. 작업이 여러 개 있으면 개별 독립 실행형 함수를 호출하는 대신 `SafeInt` 클래스를 사용해야 합니다.  
  
 T와 U 템플릿 형식에 대 한 자세한 내용은 참조 [SafeInt 함수](../windows/safeint-functions.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** microsoft:: utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 함수](../windows/safeint-functions.md)   
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)