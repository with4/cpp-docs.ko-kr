---
title: "/Z7, /Zi, /ZI(디버깅 정보 형식) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.DebugInformationFormat"
  - "/zi"
  - "/z7"
  - "VC.Project.VCCLWCECompilerTool.DebugInformationFormat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C7 호환 컴파일러 옵션[C++]"
  - "-Zl 컴파일러 옵션[C++]"
  - "디버깅 정보 형식 컴파일러 옵션"
  - "ZI 컴파일러 옵션"
  - "-Zi 컴파일러 옵션[C++]"
  - "/ZI 컴파일러 옵션[C++]"
  - "Z7 컴파일러 옵션[C++]"
  - "디버깅[C++], 디버그 정보 파일"
  - "Zi 컴파일러 옵션[C++]"
  - "none 컴파일러 옵션[C++]"
  - "/Zi 컴파일러 옵션[C++]"
  - "프로그램 데이터베이스 컴파일러 옵션[C++]"
  - "전체 기호화된 디버깅 정보"
  - "/Z7 컴파일러 옵션[C++]"
  - "줄 번호만 컴파일러 옵션[C++]"
  - "cl.exe 컴파일러, 디버깅 옵션"
  - "-Z7 컴파일러 옵션[C++]"
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: 21
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Z7, /Zi, /ZI(디버깅 정보 형식)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램용으로 생성되는 디버깅 정보 형식과 이 정보를 개체\(.obj\) 파일에 유지할지 아니면 프로그램 데이터베이스\(PDB\)에 유지할지를 선택합니다.  
  
## 구문  
  
```  
/Z{7|i|I}  
```  
  
## 설명  
 다음 표에서는 이러한 옵션에 대해 설명합니다.  
  
 없음  
 디버깅 정보를 생성하지 않으므로 컴파일 속도가 빨라집니다.  
  
 **\/Z7**  
 디버거와 함께 사용할 모든 기호 디버깅 정보가 들어 있는 .obj 파일을 생성합니다.  기호 디버깅 정보에는 변수의 이름과 형식, 함수 및 줄 번호가 들어 있습니다.  .pdb 파일은 생성되지 않습니다.  
  
 타사 라이브러리 배포자의 경우 .pdb 파일을 사용할 필요가 없다는 이점이 있습니다.  그러나 미리 컴파일된 헤더에 대한 .obj 파일이 링크 단계와 디버깅 과정에 필요합니다.  .pch 개체 파일에 코드가 없고 형식 정보만 있는 경우 컴파일할 때 [\/Yl\(디버그 라이브러리에 PCH 참조 넣기\)](../../build/reference/yl-inject-pch-reference-for-debug-library.md)도 사용해야 합니다.  
  
 **\/Zi**  
 디버거에서 사용할 형식 정보와 기호 디버깅 정보를 포함하는 프로그램 데이터베이스\(PDB\)를 생성합니다.  기호 디버깅 정보에는 변수의 이름과 형식, 함수 및 줄 번호가 들어 있습니다.  
  
 **\/Zi**는 최적화에 영향을 주지 않습니다.  그러나 **\/Zi**를 사용하면 **\/debug**도 자동으로 사용됩니다. 자세한 내용은 [\/DEBUG\(디버깅 정보 생성\)](../../build/reference/debug-generate-debug-info.md)를 참조하십시오.  
  
 형식 정보가 .obj 파일이 아닌 .pdb 파일에 저장됩니다.  
  
 [\/Gm\(최소 다시 빌드 사용\)](../../build/reference/gm-enable-minimal-rebuild.md)과 **\/Zi**는 함께 사용할 수 있지만 **\/Z7**을 사용하여 컴파일할 때는 **\/Gm**을 사용할 수 없습니다.  
  
 **\/Zi** 및 **\/clr**을 사용하여 컴파일하는 경우 <xref:System.Diagnostics.DebuggableAttribute> 특성은 어셈블리 메타데이터에 포함되지 않습니다. 이 특성을 사용하려면 소스 코드를 통해 지정해야 합니다.  이 특성은 응용 프로그램의 런타임 성능에 영향을 줄 수 있습니다.  Debuggable 특성을 사용하여 성능에 영향을 주는 방법 및 성능 영향을 수정하는 방법에 대한 자세한 내용은 [쉽게 디버깅할 수 있도록 이미지 만들기](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md)를 참조하십시오.  
  
 **\/ZI**  
 위에서 설명하는 것처럼 편집하며 계속하기 기능을 지원하는 형식으로 프로그램 데이터베이스를 생성합니다.  편집하며 계속하기 디버깅을 사용하려는 경우, 이 옵션을 사용해야 합니다.  대부분의 최적화는 편집하며 계속하기와 호환되지 않으므로, **\/ZI**를 사용하면 코드의 모든 `#pragma optimize` 문이 비활성화됩니다.  
  
 **\/ZI**를 사용하면 컴파일에 [\/Gy\(함수 수준 링크 사용\)](../../build/reference/gy-enable-function-level-linking.md) 및 [\/FC\(진단 소스 코드 파일의 전체 경로\)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)가 사용됩니다.  
  
 **\/ZI**이 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)과 호환되지 않는 경우.  
  
> [!NOTE]
>  **\/ZI**는 x86을 대상으로 한 컴파일러에서만 사용할 수 있습니다. [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 또는 ARM 프로세서를 대상으로 한 컴파일러에서는 이 컴파일러 옵션을 사용할 수 없습니다.  
  
 컴파일러는 프로그램 데이터베이스의 이름을 *project*.pdb로 지정합니다.  프로젝트 없이 파일을 컴파일하는 경우 컴파일러는 VC*x*0.pdb.라는 데이터베이스를 만듭니다. 여기서 *x*는 사용 중인 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]의 주 버전입니다.  컴파일러는 이 옵션을 사용하여 만든 각 .obj 파일에 기호화된 정보와 줄 번호 정보의 위치를 가리키는 PDB의 이름을 포함합니다.  이 옵션을 사용하면 디버깅 정보가 .obj 파일이 아닌 .pdb 파일에 저장되므로 .obj 파일은 작아집니다.  
  
 이 옵션을 사용하여 컴파일된 개체에서 라이브러리를 만드는 경우, 라이브러리가 프로그램에 연결될 때 관련된 .pdb 파일을 사용할 수 있어야 합니다.  따라서 라이브러리를 분산하는 경우, PDB도 배분해야 합니다.  
  
 .pdb 파일을 사용하지 않고 디버깅 정보가 포함된 라이브러리를 만들려면, 컴파일러의 C 7.0 호환 옵션\(**\/Z7**\)을 사용해야 합니다.  미리 컴파일된 헤더 옵션을 사용하는 경우, 미리 컴파일된 헤더와 소스 코드의 나머지 부분 모두에 대한 디버깅 정보가 PDB에 저장됩니다.  **\/Yd** 옵션은 프로그램 데이터베이스 옵션이 지정되면 무시됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **디버그 정보 형식** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)