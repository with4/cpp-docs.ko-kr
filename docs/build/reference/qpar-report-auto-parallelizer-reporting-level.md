---
title: "-/Qpar-report (자동 평행 화 도우미 보고 수준) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70ae055d69341cc773b8b40ed1111b65ba5683cf
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report(자동 병렬화 도우미 보고 수준)
컴파일러의 보고 기능을 사용 하면 [자동 평행 화](../../parallel/auto-parallelization-and-auto-vectorization.md) 컴파일하는 동안 출력에 대 한 정보 메시지의 수준을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Qpar-report:{1}{2}  
```  
  
## <a name="remarks"></a>설명  
 **/Qpar-: 1**  
 평행화되는 루프에 대해 정보 메시지를 출력합니다.  
  
 **/Qpar-: 2**  
 평행화되는 루프와 평행화되지 않는 루프 둘 다에 대해 정보 메시지와 이유 코드를 출력합니다.  
  
 메시지는 stdout에 보고됩니다. 정보 메시지가 보고되지 않는 경우에는 코드에 루프가 없거나 평행화되지 않은 루프를 보고하도록 보고 수준을 설정하지 않은 것입니다. 이유 코드 및 메시지에 대 한 자세한 내용은 참조 [벡터화 도우미 및 병렬화 도우미 메시지](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)합니다.  
  
### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Visual Studio에서 /Qpar-report 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  에 **속성 페이지** 대화 상자의 **C/c + +**선택, **명령줄**합니다.  
  
3.  에 **추가 옵션** 상자에 입력 `/Qpar-report:1` 또는 `/Qpar-report:2`합니다.  
  
### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>프로그래밍 방식으로 /Qpar-report 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/Q 옵션 (하위 수준 작업)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [네이티브 코드의 병렬 프로그래밍](http://go.microsoft.com/fwlink/p/?linkid=263662)