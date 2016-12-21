---
title: "네이티브 형식에 중첩된 값 형식의 버전 문제(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "__nogc 형식 선언"
  - "__value 키워드, 중첩 시 이슈"
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 네이티브 형식에 중첩된 값 형식의 버전 문제(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클라이언트 어셈블리를 빌드하는 데 사용되는 강력한 이름의 서명된 어셈블리를 고려해 보십시오.  이 구성 요소에는 클라이언트에서 배열, 클래스 또는 네이티브 공용 구조체의 멤버에 대한 형식으로 사용되는 값 형식이 포함됩니다.  구성 요소의 이후 버전에서 값 형식의 크기나 레이아웃이 변경되면 클라이언트를 다시 컴파일해야 합니다.  
  
 [sn.exe](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)를 사용하여 키 파일을 만듭니다\(`sn -k mykey.snk`\).  
  
## 예제  
 다음은 구성 요소 샘플입니다.  
  
```  
// nested_value_types.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
[assembly:AssemblyVersion("1.0.0.*"),   
assembly:AssemblyKeyFile("mykey.snk")];  
  
public value struct S {  
   int i;  
   void Test() {  
      System::Console::WriteLine("S.i = {0}", i);  
   }  
};  
```  
  
## 예제  
 다음은 클라이언트 샘플입니다.  
  
```  
// nested_value_types_2.cpp  
// compile with: /clr  
#using <nested_value_types.dll>  
  
struct S2 {  
   S MyS1, MyS2;  
};  
  
int main() {  
   S2 MyS2a, MyS2b;  
   MyS2a.MyS1.i = 5;  
   MyS2a.MyS2.i = 6;  
   MyS2b.MyS1.i = 10;  
   MyS2b.MyS2.i = 11;  
  
   MyS2a.MyS1.Test();  
   MyS2a.MyS2.Test();  
   MyS2b.MyS1.Test();  
   MyS2b.MyS2.Test();  
}  
```  
  
## Output  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### 설명  
 그러나 nested\_value\_types.cpp에서 `struct S`에 `double d;`와 같은 다른 멤버를 추가하고 클라이언트를 다시 컴파일하지 않은 채 구성 요소를 다시 컴파일하면 <xref:System.IO.FileLoadException?displayProperty=fullName> 형식의 처리되지 않은 예외가 발생합니다.  
  
## 참고 항목  
 [관리되는 형식](../dotnet/managed-types-cpp-cli.md)