---
title: 'Hstringreference:: Hstringreference 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs:
- C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc88ea32d4384b36559a4a10da0a5975345bf0d7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference 생성자
HStringReference 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `sizeDest`  
 대상 HStringReference 버퍼의 크기를 지정하는 템플릿 매개 변수입니다.  
  
 `str`  
 와이드 문자 문자열에 대한 참조입니다.  
  
 `len`  
 이 작업에 사용할 `str` 매개 변수 버퍼의 최대 길이입니다. `len` 매개 변수가 지정되지 않으면 전체 `str` 매개 변수가 사용됩니다. `len`이 `sizeDest`보다 큰 경우 `len`이 `sizeDest`-1로 설정됩니다.  
  
 `other`  
 다른 HStringReference 개체입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 매개 변수 `str`과 동일한 크기의 새 HStringReference 개체를 초기화합니다.  
  
 두 번째 생성자는 매개 변수 `len`에 의해 지정된 크기의 새 HStringReference 개체를 초기화합니다.  
  
 세 번째 생성자의 값에 대 한 새 HStringReference 개체를 초기화 합니다.는 `other` 매개 변수를 삭제 한 다음는 `other` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)