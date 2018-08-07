---
title: 'Hstring:: Makereference 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 673d5b10706580303f179ee453495b581d96eda3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608337"
---
# <a name="hstringmakereference-method"></a>HString::MakeReference 메서드
만듭니다는 `HStringReference` 지정 된 문자열 매개 변수에서 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
### <a name="parameters"></a>매개 변수  
 *sizeDest*  
 대상의 크기를 지정 하는 템플릿 매개 변수 `HStringReference` 버퍼입니다.  
  
 *str*  
 와이드 문자 문자열에 대한 참조입니다.  
  
 *Len 함수*  
 최대 길이 *str* 이 작업에 사용할 매개 변수 버퍼입니다. 경우는 *len* 매개 변수를 지정 하지 않으면 전체 *str* 매개 변수를 사용 합니다.  
  
## <a name="return-value"></a>반환 값  
 `HStringReference` 개체는 지정 된 대로 동일한 값인 *str* 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)