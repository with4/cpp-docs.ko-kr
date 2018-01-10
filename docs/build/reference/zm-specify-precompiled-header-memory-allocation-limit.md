---
title: "-Zm (미리 컴파일된 헤더 메모리 할당 제한 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /zm
dev_langs: C++
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a45425215fcaf336c0b1630634d0adf37ba3984
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm(미리 컴파일된 헤더 메모리 할당 제한 지정)
미리 컴파일된 헤더를 생성하기 위해 컴파일러에서 할당하는 메모리의 양을 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Zmfactor  
```  
  
## <a name="arguments"></a>인수  
 `factor`  
 미리 컴파일된 헤더를 생성하기 위해 컴파일러에서 사용하는 메모리의 양을 결정하는 배율 인수입니다.  
  
 `factor` 인수는 컴파일러에 정의된 작업 버퍼의 기본 크기에 대한 퍼센트입니다. `factor`의 기본값은 100(퍼센트)이지만 그보다 크거나 작게 지정할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 이전 버전의 Visual C++의 컴파일러에서는 각각 제한이 있는 별개의 몇 가지 힙을 사용했습니다. 그러나 지금은 컴파일러에서 필요에 따라 동적으로 힙의 크기를 전체 힙 크기 한계까지 늘리기 때문에 미리 컴파일된 헤더를 생성하기 위해 고정 크기 버퍼만 필요합니다. 따라서는 **/Zm** 컴파일러 옵션은 거의 필요 하지 않습니다.  
  
 컴파일러의 힙 공간이 부족 하 게 되 고 내보냅니다는 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 사용 하면 오류 메시지가 나타난다는 **/Zm** 컴파일러 옵션을 너무 많은 메모리를 예약한 것일 수 있습니다. 제거 하는 것이 좋습니다.는 **/Zm** 옵션입니다. 컴파일러에서는 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) 오류 메시지가 발생 하면 관련 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) 메시지가 지정 된 `factor` 인수를 사용 하 여 컴파일할 때 사용 하는 **/Zm** 컴파일러 옵션입니다.  
  
 다음 표에서는 미리 컴파일된 헤더 버퍼의 기본 크기를 75MB로 가정할 경우 `factor` 인수가 메모리 할당 제한에 어떠한 영향을 미치는지를 보여 줍니다.  
  
|`factor`의 값|메모리 할당 제한|  
|-----------------------|-----------------------------|  
|10|7.5 MB|  
|100|75MB|  
|200|150 M B|  
|1000|750 MB|  
|2000|1500MB|  
  
## <a name="other-ways-to-set-the-memory-allocation-limit"></a>메모리 할당 제한을 설정하는 기타 방법  
  
#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 /Zm 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  탐색 창에서 선택 **구성 속성**, **C/c + +**, **명령줄**합니다.  
  
3.  입력은 **/Zm** 컴파일러 옵션에는 **추가 옵션** 상자입니다.  
  
#### <a name="to-set-the-zm-compiler-option-programmatically"></a>프로그래밍 방식으로 /Zm 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)