---
title: -arch (x64) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 848d229d6cf8df7d08494d0c300e082c6dc7d0a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371673"
---
# <a name="arch-x64"></a>/arch(x64)
x64에서 코드 생성 아키텍처를 지정합니다. 또한 참조 [(x86) /arch](../../build/reference/arch-x86.md) 및 [/arch (ARM)](../../build/reference/arch-arm.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/arch:[AVX|AVX2]  
```  
  
## <a name="arguments"></a>인수  
 **/arch: avx**  
 Intel Advanced Vector Extensions 명령을 사용하도록 설정합니다.  
  
 **/arch: avx2**  
 Intel 고급 벡터 확장명 2 명령을 사용하도록 설정합니다.  
  
## <a name="remarks"></a>설명  
 **/arch** 만 코드를 네이티브 함수에 대 한 생성에 영향을 줍니다. 사용 하는 경우 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 를 컴파일하려면 **/arch** 관리 되는 함수에 대 한 코드 생성에는 아무 효과가 없습니다.  
  
 `__AVX__` 전처리기 기호가 정의 된 경우는 **/arch: avx** 컴파일러 옵션을 지정 합니다. `__AVX2__` 전처리기 기호가 정의 된 경우는 **/arch: avx2** 컴파일러 옵션을 지정 합니다. 자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오. **/arch: avx2** 옵션은 Visual Studio 2013 업데이트 2 버전 12.0.34567.1에서에서 도입 되었습니다.  
  
### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>Visual Studio에서 /arch:AVX 또는 /arch:AVX2 컴파일러 옵션을 설정하려면  
  
1.  열기는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **구성 속성**, **C/c + +** 폴더입니다.  
  
3.  선택 된 **코드 생성** 속성 페이지.  
  
4.  에 **고급 명령 집합 사용** 드롭 다운 상자 **Advanced Vector Extensions (/ /arch: AVX)** 또는 **고급 벡터 확장 2 (/ /arch: AVX2)** 합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/arch (최소 CPU 아키텍처)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)