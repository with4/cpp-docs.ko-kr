---
title: -arch (ARM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 468401bcee2d627149175d022c420b8bb905c4ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="arch-arm"></a>/arch(ARM)
ARM에서 코드 생성 아키텍처를 지정합니다. 참고 항목 [(x86) /arch](../../build/reference/arch-x86.md) 및 [(x64) /arch](../../build/reference/arch-x64.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## <a name="arguments"></a>인수  
 **: armv7ve**  
 ARMv7VE 가상화 확장명 명령을 사용하도록 설정합니다.  
  
 **/arch: vfpv4**  
 ARM VFPv4 명령을 사용하도록 설정합니다. 이 옵션을 지정하지 않으면 VFPv3이 기본값입니다.  
  
## <a name="remarks"></a>설명  
 `_M_ARM_FP` 매크로 (ARM)에 대 한 줍니다, **/arch** 컴파일러 옵션 사용. 자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오.  
  
 사용 하는 경우 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 를 컴파일하려면 **/arch** 관리 되는 함수에 대 한 코드 생성에는 아무 효과가 없습니다. **/arch** 만 코드를 네이티브 함수에 대 한 생성에 영향을 줍니다.  
  
### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Visual Studio에서 /arch:ARMv7VE 또는 /arch:VFPv4 컴파일러 옵션을 설정하려면  
  
1.  열기는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  에 **추가 옵션** 상자에서 추가 `/arch:ARMv7VE` 또는 `/arch:VFPv4`합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/arch (최소 CPU 아키텍처)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)