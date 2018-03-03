---
title: "Hstring:: Set 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs:
- C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5919e1d0247cb8af17d98b7de97c33484be2128f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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