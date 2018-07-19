---
title: 'Hstring:: Set 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs:
- C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 39c227e19cdadae80f32c25515a10dd0810f5726
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882419"
---
# <a name="hstringset-method"></a>HString::Set 메서드
지정 된 와이드 문자 문자열 또는 HString 매개 변수를 현재 HString 개체가 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
HRESULT Set(  
          const wchar_t* str) throw();  
HRESULT Set(   
          const wchar_t* str,   
          unsigned int len  
           ) throw();  
HRESULT Set(  
          const HSTRING& hstr  
           ) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `str`  
 와이드 문자 문자열입니다.  
  
 `len`  
 최대 길이 `str` 현재 HString 개체가에 할당 된 매개 변수입니다.  
  
 `hstr`  
 기존 HString 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)