---
title: "-Qpar (자동 평행 화) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
dev_langs:
- C++
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 073c906e7ecdfcf933e4b91cbcf8d6a77324df76
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="qpar-auto-parallelizer"></a>/Qpar(자동 평행화 도우미)
사용 하도록 설정 된 [자동 평행 화](../../parallel/auto-parallelization-and-auto-vectorization.md) 를 자동으로 코드에서 루프를 평행 화할 수 있는 컴파일러 기능입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Qpar  
```  
  
## <a name="remarks"></a>설명  
 컴파일러가 코드에서 루프를 자동으로 평행화하면 계산이 여러 프로세서 코어로 분산됩니다. 컴파일러에서 평행화가 적절하고 평행화를 통해 성능이 향상될 것으로 확인되는 경우에만 루프가 평행화됩니다.  
  
 `#pragma loop()` 지시문은 최적화 프로그램이 특정 루프를 평행화하는 데 사용할 수 있습니다. 자세한 내용은 참조 [루프](../../preprocessor/loop.md)합니다.  
  
 자동 병렬화에 대 한 출력 메시지를 사용 하는 방법에 대 한 정보를 참조 하십시오. [/Qpar-report (자동 평행 화 도우미 보고 수준)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)합니다.  
  
### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio에서 /Qpar 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  에 **속성 페이지** 대화 상자의 **C/c + +**선택, **명령줄**합니다.  
  
3.  에 **추가 옵션** 상자에 입력 `/Qpar`합니다.  
  
### <a name="to-set-the-qpar-compiler-option-programmatically"></a>프로그래밍 방식으로 /Qpar 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/Q 옵션 (하위 수준 작업)](../../build/reference/q-options-low-level-operations.md)   
 [/Qpar-report (자동 평행 화 도우미 보고 수준)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [#pragma loop)](../../preprocessor/loop.md)   
 [네이티브 코드의 병렬 프로그래밍](http://go.microsoft.com/fwlink/p/?linkid=263662)