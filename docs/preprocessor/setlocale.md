---
title: setlocale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs:
- C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cfabfa3c83fe2ff90a6f7dbe07d5205f7a6f9a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="setlocale"></a>setlocale
와이드 문자 상수와 문자열 리터럴을 변환할 때 사용되는 로캘(국가/지역 및 언어)을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>설명  
 멀티바이트 문자를 와이드 문자로 변환하는 알고리즘이 로캘에 따라 다를 수 있으며 실행 파일이 실행될 로캘과 다른 로캘에서 컴파일이 발생할 수 있기 때문에 이 pragma는 컴파일 시간에 대상 로캘을 지정하는 방법을 제공합니다. 이 방법을 사용하면 와이드 문자 문자열이 올바른 형식으로 저장됩니다.  
  
 기본 *로캘 문자열* 은 ""입니다.  
  
 "C" 로캘은 문자열의 각 문자를 해당 값에 `wchar_t`(unsigned short)로 매핑합니다. 에 대 한 유효한 다른 값 `setlocale` 에 있는 항목의 [언어 문자열](../c-runtime-library/language-strings.md) 목록입니다. 예를 들어 다음을 실행할 수 있습니다.  
  
```  
#pragma setlocale("dutch")  
```  
  
 언어 문자열을 실행할 수 있는지 여부는 코드 페이지와 컴퓨터의 언어 ID 지원에 따라 결정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)