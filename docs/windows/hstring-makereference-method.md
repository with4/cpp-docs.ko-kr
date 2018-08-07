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
ms.openlocfilehash: e30b3ea3c6b791eb654a6fbbe91b3c87353f31c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882643"
---
# <a name="hstringmakereference-method"></a>HString::MakeReference 메서드
지정 된 문자열 매개 변수에서 HStringReference 개체를 만듭니다.  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `sizeDest`  
 대상 HStringReference 버퍼의 크기를 지정하는 템플릿 매개 변수입니다.  
  
 `str`  
 와이드 문자 문자열에 대한 참조입니다.  
  
 `len`  
 이 작업에 사용할 `str` 매개 변수 버퍼의 최대 길이입니다. `len` 매개 변수가 지정되지 않으면 전체 `str` 매개 변수가 사용됩니다.  
  
## <a name="return-value"></a>반환 값  
 HStringReference 개체를 해당 값은 지정 된 동일 `str` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)