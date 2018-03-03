---
title: "-Qimprecise_fwaits (Try 블록 내의 fwait 제거) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Qimprecise_fwaits
dev_langs:
- C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 06c93e60530d870b05c601be4980308feb627b46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits(Try 블록 내의 fwait 제거)
제거는 `fwait` 명령 내부에 `try` 사용 하는 경우 차단는 [/fp: 제외한](../../build/reference/fp-specify-floating-point-behavior.md) 컴파일러 옵션입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Qimprecise_fwaits  
```  
  
## <a name="remarks"></a>설명  
 이 옵션은 아무런 영향을 주지 **/fp: 제외 하 고** 도 지정 하지 않으면 합니다. 지정 하는 경우는 **/fp: 제외 하 고** 옵션을 컴파일러를 삽입 하는 한 `fwait` 각 줄의 코드 주위 명령을 `try` 블록입니다. 이러한 방식으로 컴파일러가 예외를 생성 하는 코드의 특정 줄을 식별할 수 있습니다. **/Qimprecise_fwaits** 제거 내부 `fwait` 주위의 wait만 남게 지침의 `try` 블록입니다. 이 경우 성능이 향상 되지만 컴파일러는 말할 수만 `try` 블록 하면 예외가 줄 되지 않습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/Q 옵션 (하위 수준 작업)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)