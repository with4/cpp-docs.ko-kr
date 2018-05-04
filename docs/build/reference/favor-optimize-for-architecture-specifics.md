---
title: -favor (아키텍처에 대 한 최적화) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /favor
dev_langs:
- C++
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91f91373eef29adcb9a632e80520ed6713d3e39b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor(아키텍처에 맞게 최적화)
**/favor:** `option` 특정 아키텍처에 대 한 또는 AMD 및 Intel 아키텍처에서 마이크로 아키텍처 사양에 최적화 된 코드를 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## <a name="remarks"></a>설명  
 **/favor:blend**  
 (x86 및 x64)는 AMD 및 Intel 아키텍처에서 마이크로 아키텍처 사양에 맞게 최적화된 코드를 생성합니다. 반면 **/favor:blend** 최상의 성능을 제공 하지 못할 수도 x86 및 x64 프로세서의 광범위 한 최상의 성능을 제공 하도록 설계 특정 프로세서에 대해 않았습니다. 기본적으로 **/favor:blend** 적용 됩니다.  
  
 **/favor:ATOM**  
 (x86 및 x64)은 Intel Atom 프로세서 및 Intel Centrino Atom 프로세서 기술 사양에 맞게 최적화된 코드를 생성합니다. 사용 하 여 생성 된 코드는 **/favor:ATOM** Intel 프로세서에 대 한 지침을 Intel SSSE3, SSE3, SSE2 및 SSE 명령도 생성 합니다.  
  
 **/favor:AMD64**  
 (x64만 해당)는 AMD Opteron 및 64비트 확장을 지원하는 Athlon 프로세서에 대해 생성된 코드를 최적화합니다. 최적화된 코드는 모든 x64 호환 플랫폼에서 실행할 수 있습니다. 사용 하 여 생성 된 코드는 **/favor:AMD64** Intel64를 지 원하는 Intel 프로세서에서 성능이 저하 될 수 있습니다.  
  
 **/favor:INTEL64**  
 (x64만 해당)는 Intel64를 지원하는 Intel 프로세서에 대해 생성된 코드를 최적화하며 일반적으로 해당 플랫폼에서 더 나은 성능을 제공합니다. 결과 코드는 모든 x64 플랫폼에서 실행할 수 있습니다. 코드와 생성 되는 **/favor:INTEL64** AMD Opteron 및 64 비트 확장을 지 원하는 Athlon 프로세서에서 성능이 저하 될 수 있습니다.  
  
> [!NOTE]
>  Intel64 아키텍처는 이전에 확장 메모리 64 기술으로 알려졌습니다 되었으며 해당 컴파일러 옵션 **/favor:EM64T**합니다.  
  
 에 대 한 프로그래밍 하는 방법에 대 한 내용은 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 아키텍처 참조 [x64 소프트웨어 규칙](../../build/x64-software-conventions.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  입력에 컴파일러 옵션은 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)