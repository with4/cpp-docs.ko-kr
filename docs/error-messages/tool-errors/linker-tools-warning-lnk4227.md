---
title: "링커 도구 경고 LNK4227 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4227"
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 링커 도구 경고 LNK4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메타데이터 작업 경고\(HRESULT\) : warning\_message  
  
 링커에서 다음과 같은 병합 작업 도중 메타데이터에서 차이점을 발견했습니다.  
  
-   현재 빌드되는 어셈블리와 하나 이상의 참조된 어셈블리를 병합  
  
-   컴파일 도중 하나 이상의 소스 코드 파일을 병합  
  
 예를 들어 두 전역 함수의 이름이 동일하지만 매개 변수 정보가 다르게 선언된 경우\(선언이 전체 컴파일 대상에 걸쳐 일치하지 않는 경우\) LNK4227이 발생할 수 있습니다.  각 .obj 파일에 ildasm.exe \/TEXT \/METADATA `object_file`을 사용하면 형식 간의 차이를 확인할 수 있습니다.  
  
 LNK4227은 다른 도구로 인해 발생한 문제도 보고합니다.  예를 들어, al.exe로 인해 발생한 문제는 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/ko-kr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)를 참조하십시오.  
  
 이 경고를 해결하려면 메타데이터 문제를 수정해야 합니다.  
  
 예를 들어, LNK4227은 참조된 어셈블리가 이 어셈블리를 참조하는 어셈블리와 다르게 서명된 경우 발생합니다.  
  
 다음 샘플에서는 LNK4227 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 두 번째 코드 파일:  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
 다음 샘플에서는 LNK4227 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4227c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 두 번째 코드 파일:  
  
```  
// LNK4227d.cpp  
// compile with: /clr:oldSyntax LNK4227c.cpp /FeLNK4227d.exe  
#using <mscorlib.dll>  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
  
__gc class MyClass  
{  
};  
```  
  
 형식이 잘못된 버전 번호가 어셈블리 특성에 전달되는 경우에도 LNK4227이 발생될 수 있습니다.  '\*' 표기법은 AssemblyVersionAttribute에만 해당합니다.  이 경고를 해결하려면 AssemblyVersionAttribute 이외의 버전 특성에는 숫자만 사용하십시오.  
  
 다음 샘플에서는 LNK4227 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```