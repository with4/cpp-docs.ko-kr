---
title: -유효성 검사-문자 집합 (호환 문자에 대 한 유효성 검사) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0804d9d2714cc8c4f065b6908788c067c34ca44b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset (호환 문자에 대 한 유효성 검사)
소스 파일 텍스트 표현할 수 있는 문자만 포함 되어 있는지 확인 F-8입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/validate-charset[-]  
```  
  
## <a name="remarks"></a>설명  
 사용할 수는 **/validate-charset** 소스 코드가 포함 되어 있음을 소스 문자에 나타낼 수 있는 문자 집합과 실행 문자 집합의 유효성을 검사 하는 옵션입니다. 지정 하는 경우이 확인을 자동으로 사용 **/source-charset**, **/execution-charset**, 또는 **/utf-8** 컴파일러 옵션입니다. 지정 하 여이 확인을 명시적으로 비활성화할 수 있습니다는 **/ v-charset-** 옵션입니다.  
  
 기본적으로 Visual Studio 인지를 확인 하는 경우 소스 파일 인코딩된 유니코드 형식으로 예를 들어 u t F-16 u t F-8 바이트 순서 표시를 검색 합니다. 바이트 순서 표시가 없으면 발견 되 면 것으로 간주 되어 소스 파일은 인코딩된 현재 사용자 코드 페이지를 사용 하 여 코드 페이지를 사용 하 여 지정 하지 않는 한 **/utf-8** 또는 **/source-charset** 옵션입니다. Visual Studio를 사용 하면 여러 문자 인코딩 중 하나를 사용 하 여 c + + 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대 한 정보를 참조 하십시오. [문자 집합](../../cpp/character-sets.md) 언어 설명서에 있습니다. 목록은 지원 코드 페이지 식별자와 문자 집합 이름, 참조 [코드 페이지 식별자](http://msdn.microsoft.com/library/windows/desktop/dd317756)합니다.  
  
 Visual Studio는 소스 문자 집합과 실행 문자 집합 변환 시 내부 문자 인코딩으로 u t F-8을 사용 합니다. 실행 문자 집합의 원본 파일의 문자를 표현할 수 없는 경우 u t F-8로 변환 된 매개 변수를 대체 하는 '?' 문자가 있습니다. **/validate-charset** 옵션을 사용 하면이 문제가 발생 하는 경우 경고를 보고 하기 위해 컴파일 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성**, **C/c + +**, **명령줄** 폴더입니다.  
  
3.  **고급 옵션**, 추가 된 **/validate-charset** 옵션을 기본 설정 인코딩을 지정 합니다.  
  
4.  선택 **확인** 변경 내용을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (실행 문자 집합 설정)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/source-charset (소스 문자 집합 설정)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8(소스 및 실행 파일 문자 집합을 UTF-8로 설정)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)