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
ms.openlocfilehash: 7dce8c6fca14ad26665bf4868681234374c20f85
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608146"
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference 생성자
새 인스턴스를 초기화 합니다 **HStringReference** 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *sizeDest*  
 대상의 크기를 지정 하는 템플릿 매개 변수 **HStringReference** 버퍼입니다.  
  
 *str*  
 와이드 문자 문자열에 대한 참조입니다.  
  
 *Len 함수*  
 최대 길이 *str* 이 작업에 사용할 매개 변수 버퍼입니다. 경우는 *len* 매개 변수를 지정 하지 않으면 전체 *str* 매개 변수를 사용 합니다. 하는 경우 *len* 보다 크면 *sizeDest*를 *len* 로 설정 되어 *sizeDest*-1입니다.  
  
 *other*  
 다른 **HStringReference** 개체입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 초기화 된 새 **HStringReference** 과 동일한 크기의 매개 변수로 개체 *str*합니다.  
  
 두 번째 생성자는 새 **HStringReference** 개체를 매개 변수로 지정 된 크기의 *len*합니다.  
  
 세 번째 생성자는 새 **HStringReference** 개체의 값을 *다른* 매개 변수를 되지 않으며 합니다 *다른* 매개 변수.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)