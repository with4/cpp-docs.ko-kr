---
title: "-clr (공용 언어 런타임 컴파일) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a754e6c2fd8c709fd0397a2c0f78a7385819c586
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="clr-common-language-runtime-compilation"></a>/clr(공용 언어 런타임 컴파일)
응용 프로그램 및 구성 요소가 CLR(공용 언어 런타임)의 기능을 사용할 수 있게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/clr[:options]  
```  
  
## <a name="arguments"></a>인수  
 `options`  
 다음 스위치가 하나 이상 쉼표로 구분되어 있습니다.  
  
 **/clr**  
 응용 프로그램에 대한 메타데이터를 만듭니다. 메타데이터는 다른 CLR 응용 프로그램에서 사용될 수 있으며 응용 프로그램이 다른 CLR 구성 요소의 메타데이터에 있는 형식과 데이터를 사용할 수 있게 합니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
 [혼합형 (네이티브 및 관리) 어셈블리](../../dotnet/mixed-native-and-managed-assemblies.md) 및  
  
 [How to: Migrate to /clr](../../dotnet/how-to-migrate-to-clr.md).  
  
 **/clr:pure**  
 /clr:pure는 사용되지 않습니다. 이후 버전의 컴파일러는 이 옵션을 지원하지 않을 수 있습니다. C#에 대한 순수형 MSIL이어야 하는 코드를 포팅하는 것이 좋습니다.  
  
 **/clr:safe**  
 /clr:safe는 사용되지 않습니다. 이후 버전의 컴파일러는 이 옵션을 지원하지 않을 수 있습니다. C#에 대 한 안전 MSIL 이어야 하는 코드를 포팅하는 것이 좋습니다. 
  
 **/clr:noAssembly**  
 어셈블리 매니페스트를 출력 파일에 삽입하지 않도록 지정합니다. 기본적으로 **noAssembly** 옵션은 적용되지 않습니다.  
  
 **noAssembly** 옵션은 사용되지 않습니다. 대신 [/LN (Create MSIL Module)](../../build/reference/ln-create-msil-module.md) 를 사용하세요.  
  
 매니페스트에 어셈블리 메타데이터가 없는 관리되는 프로그램을 *모듈*이라고 합니다. **noAssembly** 옵션은 모듈을 생성하는 데만 사용할 수 있습니다. [/c](../../build/reference/c-compile-without-linking.md) 및 **/clr:noAssembly**를 사용하여 컴파일하는 경우 링커 단계에서 [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) 옵션을 지정하여 모듈을 만듭니다.  
  
 Visual C++ 2005 이전은, **/clr:noAssembly** 에 **/LD**가 필요합니다. **/clr:noAssembly** 를 지정할 때 **/LD**가 암시됩니다.  
  
 **/clr:initialAppDomain**  
 CLR 버전 1에서 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 응용 프로그램을 실행할 수 있게 합니다. 사용 하는 경우 **initialAppDomain**에서 설명 하는 문제 중 일부를 나타날 수 [버그: 관리 Visual c + + 구성 요소에 대 한 확장을 사용할 때의 AppDomainUnloaded 예외](http://go.microsoft.com/fwlink/p/?linkid=169465) microsoft 웹 사이트를 지원 합니다.  
  
 **initialAppDomain** 을 사용하여 컴파일된 응용 프로그램은 CLR 버전 1에서 지원되지 않으므로 ASP.NET을 사용하는 응용 프로그램에서 사용하면 안됩니다.  
  
 **/clr:nostdlib**  
 기본 \clr 디렉터리를 무시하도록 컴파일러에 지시합니다. System.dll과 같은 DLL의 여러 버전을 포함하는 경우 컴파일러에서 오류가 발생합니다. 이 옵션을 사용하면 컴파일하는 동안 사용할 특정 프레임워크를 지정할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 관리 코드는 CLR에서 검사 및 관리할 수 있는 코드입니다. 관리 코드는 관리되는 개체에 액세스할 수 있습니다. 자세한 내용은 [/clr Restrictions](../../build/reference/clr-restrictions.md)을 참조하십시오.  
  
 관리되는 형식을 정의 및 사용하는 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md).  
  
 **/clr** 을 사용하여 컴파일된 응용 프로그램은 관리되는 데이터를 포함할 수도 있고, 포함하지 않을 수도 있습니다.  
  
 관리 되는 응용 프로그램에서 디버깅을 사용 하려면 참조 [/ASSEMBLYDEBUG (DebuggableAttribute 추가)](../../build/reference/assemblydebug-add-debuggableattribute.md)합니다.  
  
 CLR 형식만 가비지 수집 힙에 인스턴스화됩니다. 자세한 내용은 참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)합니다. 함수를 네이티브 코드로 컴파일하려면 `unmanaged` pragma를 사용합니다. 자세한 내용은 참조 [관리, 관리 되지 않는](../../preprocessor/managed-unmanaged.md)합니다.  
  
 기본적으로 **/clr** 은 적용되지 않습니다. **/clr** 이 적용되는 경우 **/MD** 도 적용됩니다. 자세한 내용은 [/MD, /MT, /LD(런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md)를 참조하세요. **/MD** 는 표준 헤더(.h) 파일에서 동적으로 연결된 다중 스레드 버전의 런타임 루틴이 선택되도록 합니다. CLR 가비지 수집기는 보조 스레드에서 종료자를 실행하므로 관리되는 프로그래밍에 다중 스레딩이 필요합니다.  
  
 사용 하 여 컴파일하는 경우 **/c**, 여 결과 출력 파일의 CLR 형식을 지정할 수 있습니다 [/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)합니다.  
  
 **/clr** 은 **/EHa**를 암시하며, 다른 **/EH** 옵션은 **/clr**에 대해 지원되지 않습니다. 자세한 내용은 [/EH(예외 처리 모델)](../../build/reference/eh-exception-handling-model.md)를 참조하세요.  
  
 파일의 CLR 이미지 형식을 결정하는 방법에 대한 자세한 내용은 [/CLRHEADER](../../build/reference/clrheader.md)를 참조하세요.  
  
 링커의 지정된 호출에 전달되는 모든 모듈은 동일한 런타임 라이브러리 컴파일러 옵션(**/MD** or **/LD**)을 사용하여 컴파일해야 합니다.  
  
 어셈블리에 리소스를 포함하려면 [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) 링커 옵션을 사용합니다. [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)및 [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) 링커 옵션을 사용하여 어셈블리를 만드는 방법을 사용자 지정할 수도 있습니다.  
  
 **/clr** 을 사용하는 경우 `_MANAGED` 기호가 1로 정의됩니다. 자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오.  
  
 네이티브 개체 파일의 전역 변수가 먼저 초기화된 다음(실행 파일이 DLL인 경우 DllMain 중에) 관리되는 섹션의 전역 변수가 초기화됩니다(관리 코드가 실행되기 전에). `#pragma`[init_seg](../../preprocessor/init-seg.md) 만 스레드와 관리 되지 않는 범주의 초기화 순서에 영향을 줍니다.  
  
## <a name="metadata-and-unnamed-classes"></a>메타데이터 및 명명되지 않은 클래스  
 명명되지 않은 클래스는 `$UnnamedClass$`*crc-of-current-file-name*`$`*index*`$`와 같이 이름이 지정된 메타데이터에 나타납니다. 여기서 *index* 는 컴파일할 때 이름이 지정되지 않은 클래스의 순차적 개수입니다. 예를 들어 다음 코드 샘플은 메타데이터에 명명되지 않은 클래스를 생성합니다.  
  
```  
// clr_unnamed_class.cpp  
// compile by using: /clr /LD  
class {} x;  
```  
  
 메타데이터를 보려면 Ildasm.exe를 사용합니다.  
  
## <a name="managed-extensions-for-c"></a>Managed Extensions for C++  
 Visual C++에서는 **/clr:oldsyntax** 옵션을 더 이상 지원하지 않습니다. 이 옵션은 Visual Studio 2005에서 사용이 중단되었습니다. C++에서 관리 코드 작성에 지원되는 구문은 C++/CLI입니다. 자세한 내용은 [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md)을 참조하세요.  
  
 Managed Extensions for C++를 사용하는 코드가 있는 경우 C++/CLI 구문을 사용하도록 포팅하는 것이 좋습니다. 코드를 포팅하는 방법에 대한 자세한 내용은 [C++/CLI Migration Primer](../../dotnet/cpp-cli-migration-primer.md)을 참조하세요.  
  
#### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성** 을 클릭하여 프로젝트 **속성 페이지** 대화 상자를 엽니다.  
  
2.  **구성 속성** 폴더를 선택합니다.  
  
3.  **일반** 속성 페이지에서 **공용 언어 런타임 지원** 속성을 수정합니다.  
  
    > [!NOTE]
    >  **속성 페이지** 대화 상자에서 **/clr** 을 사용하도록 설정하는 경우 **/clr** 과 호환되지 않는 컴파일러 옵션 속성도 필요에 따라 조정됩니다. 예를 들어 **/RTC** 를 설정한 다음 **/clr** 을 사용하도록 설정하는 경우 **/RTC** 가 해제됩니다.  
    >   
    >  또한 **/clr** 응용 프로그램을 디버그하는 경우 **디버거 형식** 속성을 **혼합** 또는 **관리 전용**으로 설정합니다. 자세한 내용은 참조 [c + + 디버그 구성에 대 한 프로젝트 설정을](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)합니다.  
  
     모듈을 만드는 방법에 대 한 정보에 대 한 참조 [/NOASSEMBLY (MSIL 모듈 만들기)](../../build/reference/noassembly-create-a-msil-module.md)합니다.  
  
#### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)