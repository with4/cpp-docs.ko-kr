---
title: "-순서 (함수에 순서 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
dev_langs: C++
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2264296d288f9105a59c0ac5099c1dedef55ee2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="order-put-functions-in-order"></a>/ORDER(함수에 순서 지정)

별도로 패키지 (COMDAT) 함수에 대 한 링크 순서를 지정 합니다.

## <a name="syntax"></a>구문

>/ 순서: @*파일 이름*

### <a name="parameters"></a>매개 변수

*filename*  
COMDAT 함수에 대 한 링크 순서를 지정 하는 텍스트 파일입니다.

## <a name="remarks"></a>설명

**/순서** 컴파일러 옵션을 사용 하면 함수 호출 하는 함수를 함께 그룹화 하 여 프로그램 페이징 동작을 최적화할 수 있습니다. 또한 자주 호출된 되는 함수를 함께 그룹화 수 있습니다. 라고 하는 이러한 기법을 *스왑 조정* 또는 *페이징 최적화*, 필요 하 고 디스크에서 호출 될 필요는 없습니다 호출된 된 함수는 메모리에 있는 될 가능성이 높아집니다.

개체 파일에 소스 코드를 컴파일하는 경우 각 함수 호출 자체 섹션에 배치 하도록 컴파일러에 알 수 있습니다는 *COMDAT*를 사용 하 여는 [/Gy (함수 수준 링크 사용)](../../build/reference/gy-enable-function-level-linking.md) 컴파일러 옵션입니다. **/순서** 링커 옵션에는 Comdat 지정한 순서에 따라 실행 가능 이미지에 배치 하도록 링커에 지시 합니다.

COMDAT 순서를 지정 하려면 만듭니다는 *지시 파일*, 각 COMDAT 링커에 의해 배치 원하는 순서로 줄에 하나씩 이름별으로 나열 하는 텍스트 파일입니다. 이 파일의 이름을 전달 하는 *filename* 의 매개 변수는 **/순서** 옵션. C + + 함수에 대 한 COMDAT의 이름은 함수 이름의 데코레이팅된 형식을입니다. C 함수에 대 한 데코 레이트 되지 않은 이름을 사용 하 여 `main`로 선언 된 c + + 함수에 대 한 및 `extern "C"`합니다. 함수 이름 및 트 데코 레이 된 이름의 대/소문자 구분 됩니다. 트 데코 레이 된 이름에 대 한 자세한 내용은 참조 하십시오. [데코 레이트 된 이름](../../build/reference/decorated-names.md)합니다. 

프로그램 Comdat의 데코레이팅된 이름을 찾으려면는 [DUMPBIN](../../build/reference/dumpbin-reference.md) 도구의 [/기호](../../build/reference/symbols.md) 개체 파일에 대 한 옵션입니다. 링커 앞에 밑줄에 자동으로 추가 (\_) 함수 이름 응답에 파일 이름이 물음표 (?)로 또는 기호로 시작 하지 않는 한 (@). 예를 들어 경우 소스 파일 example.cpp, 함수가 `int cpp_func(int)`, `extern "C" int c_func(int)` 및 `int main(void)`, 명령 `DUMPBIN /SYMBOLS example.obj` 이러한 트 데코 레이 된 이름이 나열:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

이 경우, 이름 지정 `?cpp_func@@YAHH@Z`, `c_func`, 및 `main` 지시 파일에 있습니다.

개 이상의 **/순서** 링커 옵션에 옵션이 나타나면, 지정 된 마지막 트랜잭션이 적용 됩니다.

**/순서** 증분 링크 옵션을 해제 합니다. 링커 경고를 표시 될 수 있습니다 [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) 증분 링크를 사용 하는 경우 또는 지정한 경우이 옵션을 지정 하면는 [/ZI (증분 PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) 컴파일러 옵션입니다. 이 경고를 무음으로 사용할 수 있습니다는 [/incremental: no](../../build/reference/incremental-link-incrementally.md) 링커 옵션을 증분 링크를 해제 하 고 사용 하 여는 [/Zi (PDB 생성)](../../build/reference/z7-zi-zi-debug-information-format.md) 증분 링크 하지 않고 PDB를 생성 하는 컴파일러 옵션입니다.

> [!NOTE]
> 링크 정적 함수 이름이 공용 기호 이름이 없기 때문에 정적 함수 순서 수 없습니다. 때 **/순서** 지정 된 링커 경고 [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) 각 기호는 정적 이거나 찾을 수 없습니다. 순서 응답 파일에 대해 생성 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  

1. 아래 **구성 속성**개방형 **링커** 선택한 후는 **최적화** 속성 페이지.

1. 수정 된 **함수 순서** 지시 파일의 이름을 포함 하는 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[링커 옵션 설정](../../build/reference/setting-linker-options.md)  
[링커 옵션](../../build/reference/linker-options.md)