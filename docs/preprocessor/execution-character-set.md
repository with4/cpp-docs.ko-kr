---
title: execution_character_set | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
dev_langs:
- C++
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b6cb84ae6ffebda3dd335bc001463e2d8579f99
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="executioncharacterset"></a>execution_character_set
문자열 및 문자 리터럴에 사용 되는 실행 문자 집합을 지정 합니다. 이 지시어 u8 접두사가 있는 표시 된 리터럴에 대 한 필요 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma execution_character_set("target")  
```  
  
#### <a name="parameters"></a>매개 변수  
 `target`  
 대상 실행 문자 집합을 지정합니다. 현재 집합이 지원 유일한 대상 실행 "u t f-8"입니다.  
  
## <a name="remarks"></a>설명  
 컴파일러 지시문이 Visual Studio 2015 업데이트 2부터 사용 되지 않습니다. 사용 하는 것이 좋습니다는 **/execution-charset:utf-8** 또는 **/utf-8** 함께 사용 하 여 컴파일러 옵션은 `u8` 좁은 문자 및 문자열 리터럴이 포함 된 확장에 대 한 접두사 문자 수입니다. 에 대 한 자세한 내용은 `u8` 접두사, 참조 [문자열 및 문자 리터럴](../cpp/string-and-character-literals-cpp.md)합니다. 컴파일러 옵션에 대 한 자세한 내용은 참조 [(실행 문자 집합 설정) /execution-charset](../build/reference/execution-charset-set-execution-character-set.md) 및 [(원본 설정 및 실행 문자 집합을 u t F-8) /utf-8](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)합니다.  
  
 `#pragma execution_character_set("utf-8")` 지시문 실행 파일에 u t F-8로 소스 코드에서 좁은 문자열 리터럴 및 좁은 문자를 인코딩하는 데는 컴파일러가 합니다. 이 출력 인코딩은 사용 되는 소스 파일 인코딩을 무관 합니다.  
  
 기본적으로 컴파일러 실행 문자 집합으로 현재 코드 페이지를 사용 하 여 좁은 문자 및 좁은 문자열 인코딩합니다. 즉, 현재 코드 페이지의 범위 밖에 있는 리터럴에서 유니코드 또는 DBCS 문자가 출력에 기본 대체 문자를 변환 됩니다. 유니코드와 DBCS 문자는의 낮은 순서 바이트로 잘립니다. 이 거의 항상 원하지 않는입니다. 사용 하 여 소스 파일에서 리터럴에 대 한 utf-8 인코딩을 지정할 수 있습니다는 `u8` 접두사입니다. 컴파일러는 변경 되지 않은 출력에 이러한 u t F-8로 인코딩된 문자열을 전달 합니다. 좁은 문자 리터럴 u8를 사용 하 여 접두사가 1 바이트에 맞아야 합니다. 또는 출력에서 잘립니다.  
  
 기본적으로 Visual Studio 출력에 대 한 소스 코드를 해석 하는 데 사용 하는 소스 문자 집합으로 현재 코드 페이지를 사용 합니다. 파일을 읽으면 바이트 순서 표시 (BOM) 또는 u t F-16 자 파일의 시작 부분에서 검색 되는 경우가 아니면 또는 코드 페이지 파일을 설정 하지 않으면 Visual Studio 현재 코드 페이지에 따라 것을 해석 합니다. 자동 검색 BOM 없이 u t F-8로 인코딩된 소스 파일에서 발견 한 경우 현재 코드 페이지와 u t F-8을 설정할 수 없어, Visual Studio에서는 현재 코드 페이지를 사용 하 여 인코딩되지는 가정 합니다. 범위 밖에 있는 경우 지정 된 또는 자동으로 검색 된 코드 페이지는 컴파일러 경고와 오류가 발생할 수 있습니다는 소스 파일의 문자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [/execution-charset (실행 문자 집합 설정)](../build/reference/execution-charset-set-execution-character-set.md)   
 [/utf-8(소스 및 실행 파일 문자 집합을 UTF-8로 설정)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)