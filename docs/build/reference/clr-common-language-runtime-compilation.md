---
title: "-clr(공용 언어 런타임 컴파일) | Microsoft Docs"
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
  - "/CLR"
  - "VC.Project.VCNMakeTool.CompileAsManaged"
  - "VC.Project.VCCLCompilerTool.CompileAsManaged"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 공용 언어 런타임 옵션"
  - "-clr 컴파일러 옵션[C++]"
  - "clr 컴파일러 옵션[C++]"
  - "/clr 컴파일러 옵션[C++]"
  - "Managed Extensions for C++, 컴파일"
  - "공용 언어 런타임, /clr 컴파일러 옵션"
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
caps.latest.revision: 72
caps.handback.revision: 72
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /clr(공용 언어 런타임 컴파일)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램 및 구성 요소가 CLR\(공용 언어 런타임\)의 기능을 사용할 수 있게 합니다.  
  
## 구문  
  
```  
/clr[:options]  
```  
  
## 인수  
 `options`  
 다음 스위치가 하나 이상 쉼표로 구분되어 있습니다.  
  
 **\/clr**  
 응용 프로그램에 대한 메타데이터를 만듭니다. 메타데이터는 다른 CLR 응용 프로그램에서 사용될 수 있으며 응용 프로그램이 다른 CLR 구성 요소의 메타데이터에 있는 형식과 데이터를 사용할 수 있게 합니다.  
  
 詳細については、次のトピックを参照してください。  
  
 [혼합형\(네이티브 및 관리\) 어셈블리](../../dotnet/mixed-native-and-managed-assemblies.md) 및  
  
 [방법: \/clr로 마이그레이션](../../dotnet/how-to-migrate-to-clr.md).  
  
 **\/clr:pure**  
 네이티브 실행 코드가 없는 MSIL\(Microsoft Intermediate Language\) 전용 출력 파일을 생성합니다. 그러나 MSIL로 컴파일된 네이티브 형식을 포함할 수 있습니다.  
  
 자세한 내용은 [순수형 및 안정형 코드](../../dotnet/pure-and-verifiable-code-cpp-cli.md)을 참조하세요.  
  
 \/clr:pure는 사용되지 않습니다. 이후 버전의 컴파일러는 이 옵션을 지원하지 않을 수 있습니다. C\#에 대한 순수형 MSIL이어야 하는 코드를 포팅하는 것이 좋습니다.  
  
 **\/clr:safe**  
 MSIL 전용\(네이티브 실행 코드 제외\) 안전형 출력 파일을 생성합니다.**\/clr:safe**는 확인 진단\([PEVerify 도구\(Peverify.exe\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md)\)을 사용하도록 설정합니다.  
  
 자세한 내용은 [NIB: 형식 안정성이 확인된 코드 작성](http://msdn.microsoft.com/ko-kr/d18f10ef-3b48-4f47-8726-96714021547b)을 참조하세요.  
  
 \/clr:safe는 사용되지 않습니다. 이후 버전의 컴파일러는 이 옵션을 지원하지 않을 수 있습니다. C\#에 대한 순수형, 안정형 MSIL이어야 하는 코드를 포팅하는 것이 좋습니다.  
  
 **\/clr:noAssembly**  
 어셈블리 매니페스트를 출력 파일에 삽입하지 않도록 지정합니다. 기본적으로 **noAssembly** 옵션은 적용되지 않습니다.  
  
 **noAssembly** 옵션은 사용되지 않습니다. 대신 [\/LN\(MSIL 모듈 만들기\)](../../build/reference/ln-create-msil-module.md)를 사용하세요.  
  
 매니페스트에 어셈블리 메타데이터가 없는 관리되는 프로그램을 *모듈*이라고 합니다.**noAssembly** 옵션은 모듈을 생성하는 데만 사용할 수 있습니다.[\/c](../../build/reference/c-compile-without-linking.md) 및 **\/clr:noAssembly**를 사용하여 컴파일하는 경우 링커 단계에서 [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) 옵션을 지정하여 모듈을 만듭니다.  
  
 Visual C\+\+ 2005 이전은, **\/clr:noAssembly**에 **\/LD**가 필요합니다.**\/clr:noAssembly**를 지정할 때 **\/LD**가 암시됩니다.  
  
 **\/clr:initialAppDomain**  
 CLR 버전 1에서 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 응용 프로그램을 실행할 수 있게 합니다.**initialAppDomain**을 사용할 경우에는 일부 문제가 나타날 수 있습니다. 이러한 문제에 대해서는 Microsoft 지원 웹 사이트의 [버그: Visual C\+\+ 구성 요소에 대해 관리되는 확장을 사용할 때의 AppDomainUnloaded 예외](http://go.microsoft.com/fwlink/?LinkID=169465)에서 설명합니다.  
  
 **initialAppDomain**을 사용하여 컴파일된 응용 프로그램은 CLR 버전 1에서 지원되지 않으므로 ASP.NET을 사용하는 응용 프로그램에서 사용하면 안됩니다.  
  
 **\/clr:nostdlib**  
 기본 \\clr 디렉터리를 무시하도록 컴파일러에 지시합니다. System.dll과 같은 DLL의 여러 버전을 포함하는 경우 컴파일러에서 오류가 발생합니다. 이 옵션을 사용하면 컴파일하는 동안 사용할 특정 프레임워크를 지정할 수 있습니다.  
  
## 설명  
 관리 코드는 CLR에서 검사 및 관리할 수 있는 코드입니다. 관리 코드는 관리되는 개체에 액세스할 수 있습니다. 자세한 내용은 [\/clr 제한](../../build/reference/clr-restrictions.md)을 참조하십시오.  
  
 관리되는 형식을 정의 및 사용하는 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md)을 참조하세요.  
  
 **\/clr**을 사용하여 컴파일된 응용 프로그램은 관리되는 데이터를 포함할 수도 있고, 포함하지 않을 수도 있습니다.  
  
 관리되는 응용 프로그램에서 디버깅을 사용하도록 설정하려면 [\/ASSEMBLYDEBUG\(DebuggableAttribute 추가\)](../../build/reference/assemblydebug-add-debuggableattribute.md)를 참조하세요.  
  
 CLR 형식만 가비지 수집 힙에 인스턴스화됩니다. 자세한 내용은 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)을 참조하십시오. 함수를 네이티브 코드로 컴파일하려면 `unmanaged` pragma를 사용합니다. 자세한 내용은 [관리되는, 관리되지 않는](../../preprocessor/managed-unmanaged.md)을 참조하세요.  
  
 기본적으로 **\/clr**은 적용되지 않습니다.**\/clr**이 적용되는 경우 **\/MD**도 적용됩니다. 자세한 내용은 [\/MD, \/MT, \/LD\(런타임 라이브러리 사용\)](../../build/reference/md-mt-ld-use-run-time-library.md)을 참조하세요.**\/MD**는 표준 헤더\(.h\) 파일에서 동적으로 연결된 다중 스레드 버전의 런타임 루틴이 선택되도록 합니다. CLR 가비지 수집기는 보조 스레드에서 종료자를 실행하므로 관리되는 프로그래밍에 다중 스레딩이 필요합니다.  
  
 **\/c**를 사용하여 컴파일하는 경우 [\/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)을 사용하여 결과 출력 파일의 CLR 형식\(IJW, 안전 또는 순수\)을 지정할 수 있습니다.  
  
 **\/clr**은 **\/EHa**를 암시하며, 다른 **\/EH** 옵션은 **\/clr**에 대해 지원되지 않습니다. 자세한 내용은 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)을 참조하십시오.  
  
 파일의 CLR 이미지 형식을 결정하는 방법에 대한 자세한 내용은 [\/CLRHEADER](../../build/reference/clrheader.md)를 참조하세요.  
  
 링커의 지정된 호출에 전달되는 모든 모듈은 동일한 런타임 라이브러리 컴파일러 옵션\(**\/MD** or **\/LD**\)을 사용하여 컴파일해야 합니다.  
  
 어셈블리에 리소스를 포함하려면 [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) 링커 옵션을 사용합니다.[\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) 및 [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) 링커 옵션을 사용하여 어셈블리를 만드는 방법을 사용자 지정할 수도 있습니다.  
  
 **\/clr**을 사용하는 경우 `_MANAGED` 기호가 1로 정의됩니다. 자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)을 참조하십시오.  
  
 네이티브 개체 파일의 전역 변수가 먼저 초기화된 다음\(실행 파일이 DLL인 경우 DllMain 중에\) 관리되는 섹션의 전역 변수가 초기화됩니다\(관리 코드가 실행되기 전에\).`#pragma` [init\_seg](../../preprocessor/init-seg.md)는 관리되는 범주와 관리되지 않는 범주의 초기화 순서에만 영향을 줍니다.  
  
 **\/clr:safe**를 사용한 컴파일은 C\#과 같은 언어에서 [\/platform:anycpu](../Topic/-platform%20\(C%23%20Compiler%20Options\).md)를 사용하여 컴파일하는 것과 유사합니다.  
  
## 안전 및 순수 이미지  
 순수 이미지는 CLR 버전의 CRT\(C 런타임\) 라이브러리를 사용합니다. 그러나 CRT는 확인할 수 없으므로 **\/clr:safe**를 사용하여 컴파일하는 경우 CRT를 사용할 수 없습니다. 자세한 내용은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)을 참조하세요.  
  
 순수 이미지에 표시할 수 없는 네이티브 코드의 예로 인라인 어셈블리, [setjmp](../../c-runtime-library/reference/setjmp.md) 및 [longjmp](../../c-runtime-library/reference/longjmp.md)가 있습니다.  
  
 순수 이미지나 안전 이미지의 모든 진입점이 관리됩니다.**\/clr**을 사용하여 컴파일하는 경우 네이티브 진입점이 됩니다. 자세한 내용은 [\_\_clrcall](../../cpp/clrcall.md)을 참조하세요.  
  
 **\/clr:safe**를 사용하여 컴파일하는 경우 변수는 기본적으로 [appdomain](../../cpp/appdomain.md)이며 프로세스 단위가 될 수 없습니다.**\/clr:pure**의 경우 **appdomain**이 기본값이지만 [프로세스](../../cpp/process.md) 변수를 사용할 수 있습니다.  
  
 **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일된 32비트 .exe 파일을 64비트 운영 체제에서 실행하는 경우 32비트 응용 프로그램을 64비트 운영 체제의 32비트 CLR에서 실행할 수 있게 해주는 WOW64로 응용 프로그램이 실행됩니다. 기본적으로 **\/clr:safe**를 사용하여 컴파일된 .exe 파일은 64비트 운영 체제를 실행하는 컴퓨터의 64비트 CLR에서 실행됩니다. 32비트 운영 체제에서는 동일한 .exe 파일이 32비트 CLR에서 실행됩니다. 그러나 안전 응용 프로그램은 32비트 구성 요소를 로드할 수 있습니다. 이 경우 운영 체제 64비트 지원에서 실행되는 안전 이미지가 32비트 응용 프로그램을 로드할 때 실패합니다\(BadFormatException\). 64비트 운영 체제에서 32비트 이미지를 로드할 때 안전 이미지가 계속 실행되게 하려면 [\/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)을 사용하여 메타데이터\(.corflags\)를 변경하고 WOW64에서 실행되도록 표시해야 합니다. 다음 명령줄을 예로 들 수 있습니다. 사용자 고유의 항목 기호로 대체합니다.  
  
 **cl \/clr:safe t.cpp \/link \/clrimagetype:pure \/entry:?main@@$$HYMHXZ \/subsystem:console**  
  
 데코레이트된 이름을 가져오는 방법에 대한 자세한 내용은 [데코레이팅된 이름](../../build/reference/decorated-names.md)을 참조하세요. 64비트 프로그래밍에 대한 자세한 내용은 [64비트용 프로그램 구성](../../build/configuring-programs-for-64-bit-visual-cpp.md)을\(를\) 참조하십시오. 순수 CLR 코드 사용에 대한 자세한 내용은 [방법: \/clr:pure로 마이그레이션](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md) 및 [순수형 및 안정형 코드](../../dotnet/pure-and-verifiable-code-cpp-cli.md)의 내용을 참조하세요.  
  
## 메타데이터 및 명명되지 않은 클래스  
 명명되지 않은 클래스는 `$UnnamedClass$`*crc\-of\-current\-file\-name*`$`*index*`$`와 같이 이름이 지정된 메타데이터에 나타납니다. 여기서 *index*는 컴파일할 때 이름이 지정되지 않은 클래스의 순차적 개수입니다. 예를 들어 다음 코드 샘플은 메타데이터에 명명되지 않은 클래스를 생성합니다.  
  
```  
// clr_unnamed_class.cpp  
// compile by using: /clr /LD  
class {} x;  
```  
  
 메타데이터를 보려면 Ildasm.exe를 사용합니다.  
  
## Managed Extensions for C\+\+  
 Visual C\+\+에서는 **\/clr:oldsyntax** 옵션을 더 이상 지원하지 않습니다. 이 옵션은 Visual Studio 2005에서 사용이 중단되었습니다. C\+\+에서 관리 코드 작성에 지원되는 구문은 C\+\+\/CLI입니다. 자세한 내용은 [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md)을 참조하세요.  
  
 Managed Extensions for C\+\+를 사용하는 코드가 있는 경우 C\+\+\/CLI 구문을 사용하도록 포팅하는 것이 좋습니다. 코드를 포팅하는 방법에 대한 자세한 내용은 [C\+\+\/CLI 마이그레이션 입문](../../dotnet/cpp-cli-migration-primer.md)을 참조하세요.  
  
#### Visual Studio에서 이 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭하여 프로젝트 **속성 페이지** 대화 상자를 엽니다.  
  
2.  **구성 속성** 폴더를 선택합니다.  
  
3.  **일반** 속성 페이지에서 **공용 언어 런타임 지원** 속성을 수정합니다.  
  
    > [!NOTE]
    >  **속성 페이지** 대화 상자에서 **\/clr**을 사용하도록 설정하는 경우 **\/clr**과 호환되지 않는 컴파일러 옵션 속성도 필요에 따라 조정됩니다. 예를 들어 **\/RTC**를 설정한 다음 **\/clr**을 사용하도록 설정하는 경우 **\/RTC**가 해제됩니다.  
    >   
    >  또한 **\/clr** 응용 프로그램을 디버그하는 경우 **디버거 형식** 속성을 **혼합** 또는 **관리 전용**으로 설정합니다. 자세한 내용은 [C\+\+ 디버그 구성에 대한 프로젝트 설정](../Topic/Project%20Settings%20for%20a%20C++%20Debug%20Configuration.md)을 참조하십시오.  
  
     모듈을 만드는 방법에 대한 자세한 내용은 [\/NOASSEMBLY\(MSIL 모듈 만들기\)](../../build/reference/noassembly-create-a-msil-module.md)를 참조하세요.  
  
#### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged%2A>을 참조하세요.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)