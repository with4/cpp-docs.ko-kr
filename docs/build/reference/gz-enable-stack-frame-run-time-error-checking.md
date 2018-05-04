---
title: -GZ (스택 프레임 런타임 오류 검사) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gz
dev_langs:
- C++
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31224fa3b2809cbc7b7f29868ad4c3e6a89954e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ(스택 프레임 런타임 오류 검사 사용)
와 같은 작업을 수행 된 [/RTC (런타임 오류 검사)](../../build/reference/rtc-run-time-error-checks.md) 옵션입니다. 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GZ  
```  
  
## <a name="remarks"></a>설명  
 **/GZ** 는 최적화 되지 않은 빌드에 사용 하기 위한만 ([/Od (디버그 비활성화)](../../build/reference/od-disable-debug.md)) 빌드합니다.  
  
 **/GZ** Visual Studio 2005; 이후 사용은 사용 하 여 [/RTC (런타임 오류 검사)](../../build/reference/rtc-run-time-error-checks.md) 대신 합니다. 목록이 사용 되지 않는 컴파일러 옵션에 대 한 참조 **사용 되지 않음 및 컴파일러 옵션 제거** 에 [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)