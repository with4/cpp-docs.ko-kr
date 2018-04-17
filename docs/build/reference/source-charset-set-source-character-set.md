---
title: -소스-문자 집합 (집합 소스 문자 집합) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- source-charset
- /source-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba414318f9954df331dd05d0f3e2cc2b85c8ad11
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="source-charset-set-source-character-set"></a>/source-charset (소스 문자 집합 설정)
소스 문자 실행 파일의 집합을 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/source-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>인수  
 **IANA_name**  
 IANA 정의 된 문자 집합 이름입니다.  
  
 **CPID**  
 소수로 코드 페이지 식별자입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 **/source-charset** 기본 소스 문자 집합에서 표현 되지 않는 문자를 포함 하는 소스 파일을 사용 하는 확장 된 소스 문자 집합을 지정 하는 옵션입니다. 소스 문자 집합 인코딩을 컴파일 전에 전처리 단계에 대 한 입력으로 사용 되는 내부 표현으로 프로그램의 소스 텍스트를 해석 하는 데 사용 됩니다. 내부 표시는 실행 파일에 문자열 및 문자 값을 저장 하는 실행 문자 집합으로 변환 됩니다. IANA 중 하나를 사용할 수 있습니다 또는 ISO 문자 집합 이름, 점 (.)을 사용 하도록 설정 하는 문자를 지정 하려면 3 ~ 5 자리 10 진수 코드 페이지 식별자가 옵니다. 목록은 지원 코드 페이지 식별자와 문자 집합 이름, 참조 [코드 페이지 식별자](http://msdn.microsoft.com/library/windows/desktop/dd317756)합니다.  
  
 기본적으로 Visual Studio 인지를 확인 하는 경우 소스 파일 인코딩된 유니코드 형식으로 예를 들어 u t F-16 u t F-8 바이트 순서 표시를 검색 합니다. 바이트 순서 표시가 없으면 발견 되 면 것으로 간주 되어 소스 파일은 인코딩된 현재 사용자 코드 페이지를 사용 하 여 문자를 사용 하 여 이름 또는 코드 페이지 집합을 지정 하지 않으면는 **/source-charset** 옵션입니다. Visual Studio를 사용 하면 여러 문자 인코딩 중 하나를 사용 하 여 c + + 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대 한 자세한 내용은 참조 [문자 집합](../../cpp/character-sets.md) 언어 설명서에 있습니다.  
  
 소스 문자 집합을 제공 하는 문자 집합에 같은 코드 포인트에 7 비트 ASCII 문자 매핑되어야 또는 많은 컴파일 오류는 잘 합니다. 소스 문자 집합은 확장 된 유니코드 문자 u t F-8로 인코딩할 수 집합으로 매핑 가능한 수도 있어야 합니다. U t F-8에서 인코딩할 수 없는 문자가 구현의 대체도 표시 됩니다. Microsoft 컴파일러는 이러한 문자에 대 한 매개 변수를 사용합니다.  
  
 U t F-8로는 소스 문자 집합과 실행 문자 집합을 설정 하려는 경우 사용할 수 있습니다는 **/utf-8** 가기로 컴파일러 옵션입니다. 지정 하는 것과 같습니다 **/소스-charset:utf-8 /execution-charset:utf-8** 명령줄에서. 이들 옵션 사용도는 **/validate-charset** 기본적으로 옵션입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성**, **C/c + +**, **명령줄** 폴더입니다.  
  
3.  **고급 옵션**, 추가 된 **/source-charset** 옵션을 기본 설정 인코딩을 지정 합니다.  
  
4.  선택 **확인** 변경 내용을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (실행 문자 집합 설정)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/utf-8 (소스 설정 및 실행 문자 집합을 u t F-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset(호환 문자에 대한 유효성 검사)](../../build/reference/validate-charset-validate-for-compatible-characters.md)