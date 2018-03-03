---
title: "-실행-문자 집합 (집합 실행 문자 집합) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- execution-charset
- /execution-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cfb315c0dece0edc6228f70ed3900be80543cc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="execution-charset-set-execution-character-set"></a>/execution-charset (실행 문자 집합 설정)
실행 문자 집합 실행 파일을 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>인수  
 **IANA_name**  
 IANA 정의 된 문자 집합 이름입니다.  
  
 **CPID**  
 코드 페이지 식별자입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 **/execution-charset** 실행 문자 집합을 지정 하는 옵션입니다. 실행 문자 집합은 결국 전처리 단계 컴파일 단계에 대 한 입력은 프로그램의 텍스트에 사용 되는 인코딩입니다. 이 문자 집합은 컴파일된 코드에서 문자열 또는 문자 리터럴을 내부 표현에 사용 됩니다. 기본 실행 문자 집합으로 표현할 수 없는 문자를 포함 하는 소스 파일을 사용 하도록 확장 된 실행 문자 집합을 지정 하려면이 옵션을 설정 합니다. IANA 중 하나를 사용할 수 있습니다 또는 ISO 문자 집합 이름, 점 (.)을 사용 하도록 설정 하는 문자를 지정 하려면 3 ~ 5 자리 10 진수 코드 페이지 식별자가 옵니다. 목록은 지원 코드 페이지 식별자와 문자 집합 이름, 참조 [코드 페이지 식별자](http://msdn.microsoft.com/library/windows/desktop/dd317756)합니다.  
  
 기본적으로 Visual Studio 인지를 확인 하는 경우 소스 파일 인코딩된 유니코드 형식으로 예를 들어 u t F-16 u t F-8 바이트 순서 표시를 검색 합니다. 바이트 순서 표시가 없으면 발견 되 면 것으로 간주 되어 소스 파일은 인코딩된 현재 사용자 코드 페이지를 사용 하 여 문자를 사용 하 여 이름 또는 코드 페이지 집합을 지정 전 까지는 **/source-charset** 옵션 또는 **/utf-8** 옵션입니다. Visual Studio를 사용 하면 여러 문자 인코딩 중 하나를 사용 하 여 c + + 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대 한 정보를 참조 하십시오. [문자 집합](../../cpp/character-sets2.md) 언어 설명서에 있습니다.  
  
 U t F-8로는 소스 문자 집합과 실행 문자 집합을 설정 하려는 경우 사용할 수 있습니다는 **/utf-8** 가기로 컴파일러 옵션입니다. 지정 하는 것과 같습니다 **/소스-charset:utf-8 /execution-charset:utf-8** 명령줄에서. 이들 옵션 사용도는 **/validate-charset** 기본적으로 옵션입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성**, **C/c + +**, **명령줄** 폴더입니다.  
  
3.  **고급 옵션**, 추가 된 **/execution-charset** 옵션을 기본 설정 인코딩을 지정 합니다.  
  
4.  선택 **확인** 변경 내용을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/source-charset (소스 문자 집합 설정)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8 (소스 설정 및 실행 문자 집합을 u t F-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset (호환 문자에 대 한 유효성 검사)](../../build/reference/validate-charset-validate-for-compatible-characters.md)