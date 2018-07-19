---
title: -Gs (스택 검사 호출 제어) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /GS
dev_langs:
- C++
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5665187548b1f8ace41bed281684f1a830c0ad4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375742"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs(스택 검사 호출 제어)
스택 프로브를 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Gs[size]  
```  
  
## <a name="arguments"></a>인수  
 `size`  
 (옵션) 스택 프로브가 초기화되기 전에 지역 변수가 차지할 수 있는 바이트 수 입니다. 경우는 **/Gs** 옵션 없이 지정 된는 `size` 인수를 지정할 때와 동일 **/Gs0**,  
  
## <a name="remarks"></a>설명  
 스택 프로브는 컴파일러에서 모든 함수 호출에 삽입하는 코드 시퀀스입니다. 초기화되면 스택 프로브는 함수의 지역 변수를 저장하는 데 필요한 메모리 공간에 원활하게 도달합니다.  
  
 함수에서 지역 변수에 `size`바이트의 스택 공간을 필요로 하는 경우 스택 프로브가 초기화됩니다. 기본적으로 컴파일러에서는 함수에 스택 공간이 2페이지 이상 필요한 경우 스택 프로브를 초기화하는 코드를 생성합니다. 컴파일러 옵션과 같습니다 **/Gs4096** x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], 및 ARM 플랫폼입니다. 이 값은 응용 프로그램 및 Windows 메모리 관리자가 런타임 시 프로그램 스택으로 동적으로 커밋되는 메모리 양을 늘리도록 합니다.  
  
> [!NOTE]
>  기본값 **/Gs4096** 프로그램 스택이 런타임 시 올바르게 증가 하는 Windows 응용 프로그램의 합니다. 변경해야 할 확실한 이유가 없는 경우에는 이 기본값을 변경하지 마세요.  
  
 가상 장치 드라이버와 같은 일부 프로그램에는 이러한 기본 스택 증가 메커니즘이 필요하지 않습니다. 이러한 경우 스택 프로브는 필수가 아니므로 `size`를 모든 함수의 지역 변수 저장소에 필요한 것보다 더 큰 값으로 설정하여 컴파일러에서 스택 프로브 생성을 중지할 수 있습니다. 공간이 허용 되지 사이의 **/Gs** 및 `size`합니다.  
  
 **/Gs0** 지역 변수에 대 한 저장소를 필요로 하는 모든 함수 호출에 대 한 스택 프로브를 활성화 합니다. 이는 성능을 저하시킬 수 있습니다.  
  
 사용 하 여 설정 하거나 해제 하는 스택 프로브를 설정할 수 있습니다 [check_stack](../../preprocessor/check-stack.md)합니다. **/Gs** 및 `check_stack` pragma는 표준 C 라이브러리 루틴에 영향을 주지 컴파일한 함수에만 영향을 미칩니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)