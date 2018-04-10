---
title: -f-8 (원본 설정 및 실행 문자 집합을 u t F-8) | Microsoft Docs
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
- /utf-8
dev_langs:
- C++
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 592cba779113a6658b40d0dc3f855f53fa3d170c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/utf-8 (소스 설정 및 실행 문자 집합을 u t F-8)
소스 문자 집합 및 u t F-8로 실행 문자 집합을 모두 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/utf-8  
```  
  
## <a name="remarks"></a>설명  
 사용할 수는 **/utf-8** u t F-8을 사용 하 여 인코딩된으로 소스 및 실행 문자 집합을 지정 하는 옵션입니다. 지정 하는 것과 같습니다 **/소스-charset:utf-8 /execution-charset:utf-8** 명령줄에서. 이들 옵션 사용도는 **/validate-charset** 기본적으로 옵션입니다. 목록은 지원 코드 페이지 식별자와 문자 집합 이름, 참조 [코드 페이지 식별자](http://msdn.microsoft.com/library/windows/desktop/dd317756)합니다.  
  
 기본적으로 Visual Studio 인지를 확인 하는 경우 소스 파일 인코딩된 유니코드 형식으로 예를 들어 u t F-16 u t F-8 바이트 순서 표시를 검색 합니다. 바이트 순서 표시가 없으면 발견 되 면 것으로 간주 되어 소스 파일은 인코딩된 현재 사용자 코드 페이지를 사용 하 여 코드 페이지를 사용 하 여 지정 하지 않는 한 **/utf-8** 또는 **/source-charset** 옵션입니다. Visual Studio를 사용 하면 여러 문자 인코딩 중 하나를 사용 하 여 c + + 소스 코드를 저장할 수 있습니다. 소스 및 실행 문자 집합에 대 한 정보를 참조 하십시오. [문자 집합](../../cpp/character-sets2.md) 언어 설명서에 있습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성**, **C/c + +**, **명령줄** 폴더입니다.  
  
3.  **고급 옵션**, 추가 된 **/utf-8** 옵션을 기본 설정 인코딩을 지정 합니다.  
  
4.  선택 **확인** 변경 내용을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/execution-charset (실행 문자 집합 설정)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/source-charset (소스 문자 집합 설정)](../../build/reference/source-charset-set-source-character-set.md)   
 [/validate-charset (호환 문자에 대 한 유효성 검사)](../../build/reference/validate-charset-validate-for-compatible-characters.md)