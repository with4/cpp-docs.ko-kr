---
title: "링커 입력 파일로 사용하는 .netmodule 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".netmodules"
  - "링크[C++], 모듈"
  - "모듈, Visual C++"
  - "MSIL 링크"
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 입력 파일로 사용하는 .netmodule 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

link.exe 현재 입력으로 MSIL.obj 및.netmodule 받아들입니다.  링커에 의해 생성 된 출력 파일은 어셈블리 또는.netmodule.obj 또는.netmodule를 링커에 입력 된에 없으면 런타임에 종속 된 됩니다.  
  
 .netmodule은 Visual C\+\+ 컴파일러에서 [\/LN\(MSIL 모듈 만들기\)](../../build/reference/ln-create-msil-module.md)을 사용하여 만들거나 링커에서 [\/NOASSEMBLY\(MSIL 모듈 만들기\)](../../build/reference/noassembly-create-a-msil-module.md)를 사용하여 만듭니다. .obj는 항상 Visual C\+\+ 컴파일을 통해 만들어집니다.  다른 Visual Studio 컴파일러의 경우에는 **\/target:module** 컴파일러 옵션을 사용합니다.  
  
 .obj 파일은.netmodule를 만든 Visual C\+\+ 컴파일에서 .netmodule를 만들지 않았으면 할 대부분의 경우에서 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 만들어졌습니다.  Visual C\+\+ 컴파일러에서 **\/clr:safe**를 사용하여 만들 수 있는 순수 MSIL.netmodule이어야 합니다.  다른 Visual Studio 컴파일러에서는 기본적으로 순수 MSIL 모듈을 생성합니다.  
  
 명령줄에서 링커를 실행하는 방법에 대한 자세한 내용은 [링커 명령줄 구문](../../build/reference/linker-command-line-syntax.md) 및 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하십시오.  
  
 **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일한 .netmodule 또는 .dll 파일을 링커에 전달하면 링커 오류가 발생할 수 있습니다.  자세한 내용은 [.netmodule 입력 파일 형식 선택](../../build/reference/choosing-the-format-of-netmodule-input-files.md)을 참조하십시오.  
  
 링커에서는 **\/clr**, **\/clr:pure** 또는 **\/clr:safe**를 사용하여 컴파일된 MSIL .obj 파일 및 네이티브 .obj 파일을 입력으로 사용합니다.  동일한 빌드에서 혼합 .obj를 전달하면 결과 출력 파일의 확인 가능성은 기본적으로 입력 모듈의 최하위 확인 가능성과 동일해집니다.  예를 들어 링커에 안전하고 순수한 .obj를 전달하면 출력 파일은 순수해집니다.  필요한 경우 [\/CLRIMAGETYPE\(CLR 이미지 형식 지정\)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)을 사용하여 하위 확인 가능성을 지정할 수 있습니다.  
  
 현재 여러 개의 어셈블리로 구성된 응용 프로그램이 있고, 하나의 어셈블리에 응용 프로그램을 포함시키려면 어셈블리를 다시 컴파일한 다음 .obj 또는 .netmodule을 링크하여 하나의 어셈블리를 재컴파일해야 합니다.  
  
 실행 가능 이미지를 만들 때는 [\/ENTRY\(진입점 기호\)](../../build/reference/entry-entry-point-symbol.md)를 사용하여 진입점을 지정해야 합니다.  
  
 MSIL.obj 또는.netmodule 파일에 링크를 사용 하 여 [\/LTCG\(링크 타임 코드 생성\)](../../build/reference/ltcg-link-time-code-generation.md), 그렇지 않으면 링커가 MSIL.obj 또는.netmodule를 만날 때 다시 시작 됩니다 \/LTCG을 링크 합니다.  
  
 MSIL .obj에 전달할 수도 있습니다.  
  
 입력된 MSIL.obj 또는.netmodule 파일 리소스가 포함 될 수 없습니다.  리소스는 [\/ASSEMBLYRESOURCE\(관리되는 리소스 포함\)](../../build/reference/assemblyresource-embed-a-managed-resource.md) 링커 옵션을 사용하거나 다른 Visual Studio 컴파일러에서 **\/resource** 컴파일러 옵션을 사용하여 출력 파일\(모듈 또는 어셈블리\)에 포함됩니다.  
  
 MSIL 링크를 수행하는 경우 [\/LTCG\(링크 타임 코드 생성\)](../../build/reference/ltcg-link-time-code-generation.md)를 지정하지 않으면 링크를 다시 시작한다는 정보 메시지가 표시됩니다.  이 메시지는 무시할 수 있으나, MSIL 링크에서 링커 성능을 향상시키려면 명시적으로 **\/LTCG**를 지정하는 것이 좋습니다.  
  
## 예제  
 C\+\+ 코드에서는 시스템 예외가 아닌 예외의 경우 해당 try의 catch 블록이 호출됩니다.  그러나 CLR에서는 기본적으로 시스템 예외가 아닌 예외를 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>으로 래핑합니다.  Visual C\+\+ 및 Visual C\+\+가 아닌 모듈로 어셈블리를 만든 경우 try 블록에서 시스템 예외가 아닌 예외를 throw할 때 이 try 절에서 C\+\+ 코드의 catch 블록을 호출하도록 하려면 C\+\+가 아닌 모듈의 소스 코드에 다음 특성을 추가해야 합니다.  
  
 \[assembly:System::Runtime::CompilerServices::RuntimeCompatibility\(WrapNonExceptionThrows\=false\)\]  
  
```  
// MSIL_linking.cpp  
// compile with: /c /clr  
value struct V {};  
  
ref struct MCPP {  
   static void Test() {  
      try {  
         throw (gcnew V);  
      }  
      catch (V ^) {  
         System::Console::WriteLine("caught non System exception in C++ source code file");  
      }  
   }  
};  
  
/*  
int main() {  
   MCPP::Test();  
}  
*/  
```  
  
## 예제  
 WrapNonExceptionThrows 특성의 부울 값을 변경하면 Visual C\+\+ 코드에서 시스템 예외가 아닌 예외를 catch할 수 있는지 여부가 수정됩니다.  
  
```  
// MSIL_linking_2.cs  
// compile with: /target:module /addmodule:MSIL_linking.obj  
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console  
using System.Runtime.CompilerServices;  
  
// enable non System exceptions  
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]  
  
class MLinkTest {  
   public static void Main() {  
      try {  
         MCPP.Test();  
      }  
      catch (RuntimeWrappedException) {  
         System.Console.WriteLine("caught a wrapped exception in C#");  
      }  
   }  
}  
```  
  
  **c \+ \+ 소스 코드 파일에서 시스템 예외가 아닌 예외 catch**   
## 참고 항목  
 [LINK 입력 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)