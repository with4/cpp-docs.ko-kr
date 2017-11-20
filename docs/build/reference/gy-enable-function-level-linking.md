---
title: "-Gy (함수 수준 링크 사용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
dev_langs: C++
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e7d83e4409d9c46c926859f39029ea68f2411def
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="gy-enable-function-level-linking"></a>/Gy(함수 수준 링크 사용)
컴파일러가 개별 함수를 패키지 형식으로 패키지 함수 (Comdat).  
  
## <a name="syntax"></a>구문  
  
```  
/Gy[-]  
```  
  
## <a name="remarks"></a>설명  
 링커에서 함수를 제외 하거나 DLL 또는.exe 파일의 개별 함수를 정렬 하는 Comdat로 별도로 패키지할 수 있습니다.  
  
 링커 옵션을 사용할 수 있습니다 [/OPT (최적화)](../../build/reference/opt-optimizations.md) .exe 파일에서 참조 되지 않는 패키지에 포함 된 함수를 제외 합니다.  
  
 링커 옵션을 사용할 수 있습니다 [/ORDER (순서 대로 배치 함수)](../../build/reference/order-put-functions-in-order.md) .exe 파일에 지정된 된 순서에 패키지 된 함수를 포함 하도록 합니다.  
  
 인라인 함수는 호출으로 인스턴스화되는 경우 항상 패키지로 (있는 경우 예를 들어 인라인 처리 해제 되었거나 함수 주소를 사용). 또한 클래스 선언에 정의 된 c + + 멤버 함수 자동으로 패키지 됩니다. 다른 함수, 되지 않으며이 옵션을 선택 하면 패키지에 포함 된 함수로 컴파일할 필요 합니다.  
  
> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 편집 하며 계속 하기를 사용 하는 옵션을 자동으로 설정 합니다.는 **/Gy** 옵션입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **코드 생성** 속성 페이지.  
  
4.  수정 된 **함수 수준 링크 사용** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)