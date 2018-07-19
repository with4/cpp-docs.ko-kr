---
title: -GF (중복 문자열 제거) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
dev_langs:
- C++
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2710fe8c5cc444d9e2681620f6813312a1d65a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375895"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF(중복 문자열 제거)
컴파일러가 실행 하는 동안 프로그램 이미지에서와 메모리에 동일한 문자열의 단일 복사본을 만들 수 있습니다. 이 호출 하는 최적화 *문자열 풀링* 더 작은 프로그램을 만들 수 있는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GF  
```  
  
## <a name="remarks"></a>설명  
 사용 하는 경우 **/GF**, 운영 체제는 메모리의 문자열 부분 스왑하지 및 이미지 파일에서 해당 문자열을 다시 읽을 수 있습니다.  
  
 **/GF** 읽기 전용으로 문자열을 풀링합니다. 아래 문자열을 수정 하려고 하면 **/GF**, 응용 프로그램 오류가 발생 합니다.  
  
 문자열 풀링 기능 서로 여러 버퍼에 대 한 여러 포인터로 단일 버퍼에 대 한 여러 포인터 일 수 있습니다. 다음 코드에서 `s` 및 `t` 동일한 문자열을 사용 하 여 초기화 됩니다. 문자열 풀링 동일한 메모리를 가리키게 됩니다.  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 편집 하며 계속 하기를 사용 하는 옵션을 자동으로 설정 합니다.는 **/GF** 옵션입니다.  
  
> [!NOTE]
>  **/GF** 컴파일러 옵션은 각 고유 문자열에 대 한 주소 지정 가능한 섹션을 만듭니다. 및 개체 파일은 기본적으로 최대 65, 536 주소 지정 가능한 섹션을 포함할 수 있습니다. 65, 536 개 이상의 문자열을 포함 하는 프로그램을 사용 하 여는 [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) 컴파일러 옵션 섹션을 추가로 만들을 합니다.  
  
 **/GF** 때 적용 됩니다 [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 또는 **/O2** 사용 됩니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **코드 생성** 속성 페이지.  
  
4.  수정 된 **문자열 풀링 사용** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)