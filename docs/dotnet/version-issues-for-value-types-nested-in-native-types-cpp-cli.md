---
title: "네이티브 형식에 중첩 된 값 형식의 버전 문제 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __nogc type declarations
- __value keyword, issues when nesting
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a16b6fd7d166b7a997257bfd6cb741b82911c5bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="version-issues-for-value-types-nested-in-native-types-ccli"></a>네이티브 형식에 중첩된 값 형식의 버전 문제(C++/CLI)
클라이언트 어셈블리를 제조 하는 데 사용 하는 서명된 (강력한 이름) 어셈블리 구성 요소를 고려 합니다. 구성 요소에는 네이티브 공용 구조체, 클래스 또는 배열 멤버에 대 한 형식으로 클라이언트에 사용 되는 값 형식이 포함 되어 있습니다. 이후 버전의 구성 요소 크기 또는 값 형식의 레이아웃을 변경 하는 경우 클라이언트 다시 컴파일해야 합니다.  
  
 키와 파일을 만들려면 [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).  
  
## <a name="example"></a>예제  
 다음 샘플 구성 요소입니다.  
  
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
  
## <a name="example"></a>예제  
 이 샘플은 클라이언트:  
  
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
  
## <a name="output"></a>출력  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### <a name="comments"></a>설명  
 그러나 다른 멤버를 추가 하는 경우 `struct S` nested_value_types.cpp에 (예를 들어 `double d;`) 클라이언트를 다시 컴파일하지 않고도 구성 요소를 다시 컴파일해야 하 고, 결과 처리 되지 않은 예외가 (형식의 <xref:System.IO.FileLoadException?displayProperty=fullName>).  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 형식(C++/CLI)](../dotnet/managed-types-cpp-cli.md)