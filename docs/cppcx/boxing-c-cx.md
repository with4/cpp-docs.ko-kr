---
title: "Boxing(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# Boxing(C++/CX)
*boxing*은 [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)과 같은 값 형식 변수 또는 `int`와 같은 기본 스칼라 형식이 [Platform::Object^](../cppcx/platform-object-class.md)을 해당 입력 형식으로 사용하는 메서드에 전달될 때 해당 변수를 ref 클래스에 래핑합니다.  
  
## Object^ 매개 변수에 값 형식 전달  
 [Platform::Object^](../cppcx/platform-object-class.md) 형식의 메서드 매개 변수에 전달하기 위해 명시적으로 변수를 boxing할 필요는 없지만 이전에 boxing된 값을 검색할 때는 명시적으로 원래 형식으로 캐스팅해야 합니다.  
  
 [!code-cpp[cx_boxing#01](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.cpp#01)]  
  
### Platform::IBox\<T\>를 사용하여 null 허용 값 형식 지원  
 C\# 및 Visual Basic에서는 null 허용 값 형식의 개념을 지원합니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서는 `Platform::IBox<T>` 형식을 사용하여 null 허용 값 형식 매개 변수를 지원하는 공용 메서드를 노출할 수 있습니다. 다음 예제에서는 C\# 호출자가 인수 중 하나에 대해 null을 전달하는 경우 null을 반환하는 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 공용 메서드를 보여 줍니다.  
  
 [!code-cpp[cx_boxing#02](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.h#02)]  
  
 C\# XAML 클라이언트에서 이러한 메서드를 다음과 같이 사용할 수 있습니다.  
  
```  
  
// C# client code BoxingDemo.Class1 obj = new BoxingDemo.Class1(); int? a = null; int? b = 5; var result = obj.Multiply(a,b); //result = null  
  
```  
  
## 참고 항목  
 [형식 시스템\(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [캐스팅\(C\+\+\/CX\)](../cppcx/casting-c-cx.md)   
 [Visual C\+\+ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)   
 [네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)