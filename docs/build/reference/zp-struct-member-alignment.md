---
title: -Zp (구조체 멤버 맞춤) | Microsoft Docs
ms.custom: ''
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1666da40f748d18c762eae19595692addcdbf78a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380864"
---
# <a name="zp-struct-member-alignment"></a>/Zp(구조체 멤버 맞춤)

구조체의 멤버를 메모리에 압축 되는 방식을 제어 하 고 모듈의 모든 구조에 대해 동일한 압축을 지정 합니다.

## <a name="syntax"></a>구문

> **/Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>설명

지정 하는 경우는 **/Zp**_n_ 옵션, 각 구조체 멤버가 첫 번째 멤버 형식의 크기에 저장 된 후 또는 *n*-바이트 경계 (여기서 *n* 는 1, 2, 4, 8 또는 16), 중 더 작은 값입니다.

다음 표에서에 사용할 수 있는 압축 값을 설명 하 고 있습니다.

|/Zp 인수|효과|
|-|-|
|1|1 바이트 경계에서 구조체를 압축 합니다. 와 동일 **/Zp**합니다.|
|2|2 바이트 경계에서 구조체를 압축 합니다.|
|4|4 바이트 경계에서 구조체를 압축 합니다.|
|8|(기본값) 8 바이트 경계에서 구조체를 압축 합니다.|
|16| 16 바이트 경계에서 구조체를 압축 합니다.|

특정 맞춤 요구 사항이 있는 아니라면이 옵션을 사용 하지 않아야 합니다.

> [!WARNING]  
> Windows SDK에서 c + + 헤더 가정 **/z p 8** 압축 합니다. 메모리 손상 경우 발생할 수 있습니다는 **/Zp** Windows SDK 헤더를 사용 하 여 설정을 변경 합니다.

사용할 수도 있습니다 [팩](../../preprocessor/pack.md) 제어 구조 했음입니다. 정렬에 대한 자세한 내용은 다음을 참조하십시오.

- [align](../../cpp/align-cpp.md)

- [__alignof 연산자](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [구조체 맞춤 예제](../../build/examples-of-structure-alignment.md) (x64 전용)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **C/c + +** > **코드 생성** 속성 페이지.

1. 수정 된 **구조체 멤버 맞춤** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [컴파일러 옵션](../../build/reference/compiler-options.md)   
- [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)
