---
title: "-Z7,-Zi,-ZI (디버그 정보 형식) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /zi
- /z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs: C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- -Zl compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- none compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b80339192a7d335b0989ac8a67446c0f5716a76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI(디버깅 정보 형식)
프로그램용으로 생성되는 디버깅 정보 형식과 이 정보를 개체(.obj) 파일에 유지할지 아니면 프로그램 데이터베이스(PDB)에 유지할지를 선택합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Z{7|i|I}  
```  
  
## <a name="remarks"></a>설명  
 다음 표에서는 이러한 옵션에 대해 설명합니다.  
  
 없음  
 디버깅 정보를 생성하지 않으므로 컴파일 속도가 빨라집니다.  
  
 **/Z7**  
 디버거와 함께 사용할 모든 기호 디버깅 정보가 들어 있는 .obj 파일을 생성합니다. 기호 디버깅 정보에는 변수의 이름과 형식, 함수 및 줄 번호가 들어 있습니다. .pdb 파일은 생성되지 않습니다.  
  
 타사 라이브러리 배포자의 경우 .pdb 파일을 사용할 필요가 없다는 이점이 있습니다. 그러나 미리 컴파일된 헤더에 대한 .obj 파일이 링크 단계와 디버깅 과정에 필요합니다. 로 컴파일하는 됩니다.pch 개체 파일에 정보 (및 코드 없이) 형식에 있으면 [/Yl (주입 PCH 참조 디버그 라이브러리에 대 한)](../../build/reference/yl-inject-pch-reference-for-debug-library.md)합니다.  
  
 **/Zi**  
 디버거에서 사용할 형식 정보와 기호 디버깅 정보를 포함하는 프로그램 데이터베이스(PDB)를 생성합니다. 기호 디버깅 정보에는 변수의 이름과 형식, 함수 및 줄 번호가 들어 있습니다.  
  
 **/Zi** 최적화에 영향을 주지 않습니다. 그러나 **/Zi** 의미지 않습니다 **/debug**; 참조 [/DEBUG (디버깅 정보 생성)](../../build/reference/debug-generate-debug-info.md) 자세한 정보에 대 한 합니다.  
  
 형식 정보가 .obj 파일이 아닌 .pdb 파일에 저장됩니다.  
  
 사용할 수 있습니다 [/Gm (최소 다시 빌드 가능)](../../build/reference/gm-enable-minimal-rebuild.md) 와 **/Zi**반면, **/Gm** 로 컴파일할 때 사용할 수 없으면 **/Z7**합니다.  
  
 로 컴파일할 때 **/Zi** 및 **/clr**, <xref:System.Diagnostics.DebuggableAttribute> 특성은 어셈블리 메타 데이터에 배치할 수 없습니다; 원할 경우 소스 코드에서 지정 해야 합니다. 이 특성은 응용 프로그램의 런타임 성능에 영향을 줄 수 있습니다. 디버깅 가능한 특성이 성능에 미치는 영향 및 성능에 미치는 영향을 수정 하는 방법에 대 한 자세한 내용은 참조 [이미지 쉽게 디버그 수 만들기](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)합니다.  
  
 **/ZI**  
 위에서 설명하는 것처럼 편집하며 계속하기 기능을 지원하는 형식으로 프로그램 데이터베이스를 생성합니다. 편집하며 계속하기 디버깅을 사용하려는 경우, 이 옵션을 사용해야 합니다. 대부분의 최적화 편집 하며 계속 하기와 호환 되지 않으므로 사용 하 여 **/ZI** 하나를 사용 하지 않도록 설정 `#pragma optimize` 사용자 코드에서 문입니다.  
  
 **/ZI** 하면 [/Gy (함수 수준 링크 사용)](../../build/reference/gy-enable-function-level-linking.md) 및 [/FC (전체 소스 코드 파일의 경로 진단에서)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) 컴파일에 사용할 수 있습니다.  
  
 **/ZI** 와 호환 되지 않는 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
> [!NOTE]
>  **/ZI** 은 영어로; x86 및 x64 프로세서를 대상으로 한 컴파일러가 컴파일러 옵션은 ARM 프로세서를 대상 하는 컴파일러에서 사용할 수 없습니다.  
  
 컴파일러는 프로그램 데이터베이스 이름을 *프로젝트*.pdb. 컴파일러 VC 라는 데이터베이스를 만듭니다 프로젝트 없이 파일을 컴파일하는 경우*x*0.pdb 여기서 *x* 는의 주 버전 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 사용에서 합니다. 컴파일러는 이 옵션을 사용하여 만든 각 .obj 파일에 기호화된 정보와 줄 번호 정보의 위치를 가리키는 PDB의 이름을 포함합니다. 이 옵션을 사용하면 디버깅 정보가 .obj 파일이 아닌 .pdb 파일에 저장되므로 .obj 파일은 작아집니다.  
  
 이 옵션을 사용하여 컴파일된 개체에서 라이브러리를 만드는 경우, 라이브러리가 프로그램에 연결될 때 관련된 .pdb 파일을 사용할 수 있어야 합니다. 따라서 라이브러리를 분산하는 경우, PDB도 배분해야 합니다.  
  
 .Pdb 파일을 사용 하지 않고 디버깅 정보를 포함 하는 라이브러리를 만들려면 컴파일러의 C 7.0 호환을 선택 해야 합니다 (**/Z7**) 옵션입니다. 미리 컴파일된 헤더 옵션을 사용하는 경우, 미리 컴파일된 헤더와 소스 코드의 나머지 부분 모두에 대한 디버깅 정보가 PDB에 저장됩니다. **/Yd** 프로그램 데이터베이스 옵션을 지정 하는 경우 옵션은 무시 됩니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **일반** 속성 페이지.  
  
4.  수정 된 **디버깅 정보 형식** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)