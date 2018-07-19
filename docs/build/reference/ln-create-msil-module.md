---
title: -LN (MSIL 모듈 만들기) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /LN
dev_langs:
- C++
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 918b3857c2e6f26a7f2e11614a00049e9b615ea8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375313"
---
# <a name="ln-create-msil-module"></a>/LN(MSIL 모듈 만들기)
어셈블리 매니페스트를 출력 파일에 삽입하지 않도록 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/LN  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 **/LN** (어셈블리 매니페스트는 출력 파일에 삽입 됩니다.) 적용 되지 않습니다.  
  
 때 **/LN** 을 사용 하는 중 하나는 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션 사용 해야 합니다.  
  
 매니페스트에 어셈블리 메타 데이터가 없는 관리 되는 프로그램 모듈을 이라고 합니다. 사용 하 여 컴파일하면 [/c (컴파일 없이 링크 사용)](../../build/reference/c-compile-without-linking.md) 및 **/LN**, 지정 [/NOASSEMBLY (MSIL 모듈 만들기)](../../build/reference/noassembly-create-a-msil-module.md) 링커 단계 출력 파일을 만듭니다.  
  
 원하는 하는 구성 요소 기반 방식을 사용 어셈블리를 빌드 하려는 경우 모듈을 만들 수 있습니다.  즉, 형식 제작 하 고 모듈에 컴파일할 수 있습니다.  그런 다음 하나 이상의 모듈에서 어셈블리를 생성할 수 있습니다.  모듈에서 어셈블리를 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [링커 입력 파일로.netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md) 또는 [Al.exe (어셈블리 링커)](/dotnet/framework/tools/al-exe-assembly-linker)합니다.  
  
 모듈의 기본 파일 확장명은 .netmodule입니다.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Visual c + + 2005 이전 버전에서 모듈을 사용 하 여 만든 된 **/clr:noAssembly**합니다.  
  
 Visual C++ 링커는 .netmodule 파일을 입력을 받아들이며, 링커에서 생성된 출력 파일은 링커에 입력된 .netmodules에 대해 런타임 종속성이 없는 어셈블리 또는 .netmodule입니다.  자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)을 참조하세요.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
-   지정 [/NOASSEMBLY (MSIL 모듈 만들기)](../../build/reference/noassembly-create-a-msil-module.md) 링커 단계 출력 파일을 만듭니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   이 컴파일러 옵션을 프로그래밍 방식으로 변경할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)