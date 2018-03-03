---
title: "-BASE (기준 주소) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ddf399757d881484817be676ca3077b4fc21709
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="base-base-address"></a>/BASE(기준 주소)
```  
/BASE:{address[,size] | @filename,key}  
```  
  
 기본 옵션.exe 또는 DLL 파일에 대 한 기본 위치는 프로그램에 대 한 기본 주소를 설정 합니다. .Exe 파일에 대 한 기본 기준 주소에 32 비트 이미지에 대 한 0x400000입니다 인지 0x140000000 64 비트 이미지에 대 한 합니다. DLL에 대 한 기본 기준 주소는 32 비트 이미지에 대 한 0x10000000 또는 64 비트 이미지 0x180000000 합니다. 주소 공간 레이아웃 불규칙화 (ASLR)를 지원 하지 않는 또는 /dynamicbase: no 옵션 설정 된 경우 운영 체제에서는 운영 체제는 먼저 지정 된 프로그램 또는 기본 기준 주소를 로드 시도 합니다. 사용할 수 있는 충분 한 공간이 없으면 시스템 프로그램 뒤로 다시 지정 합니다. 재배치를 방지 하려면 사용 하 여는 [고정/](../../build/reference/fixed-fixed-base-address.md) 옵션입니다.  
  
 링커에서 오류가 발생 하는 경우 *주소* 64k의 배수가 아닙니다. 필요에 따라; 프로그램의 크기를 지정할 수 있습니다. 링커에서 프로그램 지정한 크기에 맞지 않는 경고를 표시 합니다.  
  
 명령줄에서 기준 주소를 지정 하는 다른 방법은 기본 주소 응답 파일을 사용 하 여 됩니다. 기본 주소 지시 파일은 기본 주소를 프로그램에서 사용할 모든 Dll 및 각 기본 주소에 대 한 텍스트 고유 키의 선택적 크기를 포함 하는 텍스트 파일입니다. 지시 파일을 사용 하 여 기본 주소를 지정 하려면 사용는 at 기호 (@) 지시 파일의 이름이 차례로 나옵니다 *filename*, 쉼표, 세로줄 하면 `key` 파일에서 사용 하는 기본 주소에 대 한 값입니다. 링커 검색 *파일 이름* 지정 된 경로에 않거나 LIB 환경 변수에 지정 된 디렉터리에서 경로가 없는 지정 합니다. 각 줄 *filename* 하나의 DLL을 나타내며 다음 구문을 가집니다.  
  
```  
  
key address [size] ;comment  
```  
  
 `key` 영숫자 문자와 밑줄 문자는 문자열이 고 대/소문자를 무시 합니다. 일반적으로 DLL의 이름 하지만 같이 필요는 없습니다. `key` 기본 나옵니다 *주소* C 언어, 16 진수 또는 십진수 표기법 및 선택적 최대 `size`합니다. 모든 세 개의 인수는 공백이 나 탭으로 구분 됩니다. 링커 경우에서 경고가 발생 지정 된 `size` 프로그램에 필요한 가상 주소 공간 보다 작습니다. A `comment` 세미콜론 (;)으로 지정 하 고 동일 하거나 별도 줄에 있을 수 있습니다. 링커 줄의 끝에 세미콜론에서 모든 텍스트를 무시합니다. 이 예제에서는 이러한 파일의 일부를 보여 줍니다.  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 이 줄이 포함 된 파일을 DLLS.txt 라고 하는 경우 다음 예제 명령은이 정보를 적용 합니다.  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## <a name="remarks"></a>설명  
 보안상의 이유로 Microsoft에서 권장 된 [/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) 실행 파일에 대 한 기본 주소를 지정 하는 대신 옵션입니다. Windows의 주소 공간 레이아웃 불규칙화 (ASLR) 기능을 사용 하 여 로드 시간에 임의로 지정할 수 있는 실행 가능 이미지를 생성 합니다. /DYNAMICBASE 옵션 기본적으로 켜져 있습니다.  
  
 사용 하 여 기본 주소를 설정 하는 다른 방법은는 *기본* 인수에는 [이름](../../build/reference/name-c-cpp.md) 또는 [라이브러리](../../build/reference/library.md) 문. /BASE 및 [/DLL](../../build/reference/dll-build-a-dll.md) 옵션이 모두 해당 하는 **라이브러리** 문.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **링커** 폴더입니다.  
  
3.  선택 된 **고급** 속성 페이지.  
  
4.  수정 된 **기준 주소** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)