---
title: "-Zo (최적화 된 디버깅 향상) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- -Zo
- /Zo
dev_langs:
- C++
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 326bd1c6c435dec97c309014dfc81ca444cc5eb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo(최적화된 디버깅 향상)
디버그되지 않은 빌드에서 최적화된 코드에 대해 향상된 디버깅 정보를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
/Zo[-]  
```  
  
## <a name="remarks"></a>설명  
 **/Zo** 컴파일러 스위치는 최적화 된 코드에 대 한 향상 된 디버깅 정보를 생성 합니다. 최적화는 지역 변수에 레지스터를 사용하고 코드를 다시 정렬하며 루프를 벡터화하고 인라인 함수 호출을 수행할 수 있습니다. 이와 같이 최적화를 수행하면 소스 코드와 컴파일된 개체 코드 간 관계가 명확하지 않을 수 있습니다. **/Zo** 스위치는 지역 변수 및 인라인 된 함수에 대 한 추가적인 디버깅 정보를 생성 하도록 컴파일러에 지시 합니다. 변수를 사용 하 여는 **자동**, **지역**, 및 **조사식** 최적화 된 Visual Studio 디버거에서 코드를 단계별로 실행할 때 windows 합니다. 또한 스택 추적을 설정하여 WinDBG 디버거에 인라인된 함수를 표시할 수도 있습니다. 디버그 빌드를 최적화 비활성화 ([/Od](../../build/reference/od-disable-debug.md)) 때 생성 된 추가 디버깅 정보가 필요 하지 않은 **/Zo** 지정 됩니다. 사용 하 여는 **/Zo** 켜져 최적화를 사용 하 여 릴리스 구성을 디버그로 전환 합니다. 최적화 스위치에 대 한 자세한 내용은 참조 하십시오. [/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)합니다. **/Zo** 옵션은 Visual Studio에서 기본적으로 사용 하 여 디버깅 정보를 지정 하는 경우 **/Zi** 또는 **/Z7**합니다. 지정 **/Zo-** 를 명시적으로이 컴파일러 옵션을 사용 하지 않도록 설정 합니다.  
  
 **/Zo** 스위치는 Visual Studio 2013 업데이트 3부터 사용할 수 있으며 이전에 문서화 되지 않은 대체 **/d2Zi+** 전환 합니다.  
  
### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Visual Studio에서 /Zo 컴파일러 옵션을 설정하려면  
  
1.  열기는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **구성 속성**, **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  수정 된 **추가 옵션** 포함할 속성을 `/Zo` 선택한 후 **확인**합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)   
 [/Z7, /Zi, /ZI (디버깅 정보 형식)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 [편집하며 계속하기](/visualstudio/debugger/edit-and-continue)