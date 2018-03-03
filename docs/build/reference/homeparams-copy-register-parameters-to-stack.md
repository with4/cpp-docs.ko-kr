---
title: "-homeparams (레지스터 스택에 매개 변수 복사) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fff1b206620ef9efee3fc22c83c8d5317e99b607
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams(스택에 레지스터 매개 변수 복사)
레지스터에 전달된 매개 변수를 함수 시작 시 스택의 해당 위치에 기록합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/homeparams  
```  
  
## <a name="remarks"></a>설명  
 이 컴파일러 옵션은 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일러(네이티브 및 크로스 컴파일)에만 사용됩니다.  
  
 에 매개 변수가 전달 되는 경우는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일, 호출 규칙에 따라 필요 레지스터에 전달 된 매개 변수에 대해서도 매개 변수에 대 한 합니다. 자세한 내용은 참조 [매개 변수 전달](../../build/parameter-passing.md)합니다. 그러나 릴리스 빌드에서 기본적으로 레지스터 매개 변수는 쓰지을 스택에 매개 변수에 대해 제공 되는 공간으로. 이렇게 하면 프로그램의 최적화 (릴리스) 빌드를 디버그 하기 어렵습니다.  
  
 릴리스 빌드를 사용 하 여 **/homeparams** 응용 프로그램을 디버깅할 수 있도록 합니다. **/homeparams** 성능 단점은 스택에 레지스터 매개 변수를 로드 하기 위한 주기가 필요 하므로 의미는 않습니다.  
  
 디버그 빌드에서 스택의 항상 채워집니다 레지스터에 전달 된 매개 변수를 사용 합니다.  
  
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