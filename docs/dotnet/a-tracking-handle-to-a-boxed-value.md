---
title: "boxed 값에 대한 추적 핸들 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Boxed 값 형식, 추적 핸들"
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# boxed 값에 대한 추적 핸들
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 값 형식을 참조하는 추적 핸들을 사용하는 방법이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 boxing은 CLR 통합 형식 시스템의 특징입니다.  값 형식에는 자신의 상태가 직접 포함되지만, 참조 형식은 암시적인 쌍입니다. 즉, 명명된 엔터티는 관리되는 힙에 할당된 명명되지 않은 개체에 대한 핸들입니다.  예를 들어, `Object`에 값 형식을 할당하거나 값 형식을 사용하여 이를 초기화하려면 먼저 관련 메모리를 할당한 다음 값 형식의 상태를 복사하고 이 무명 값\/참조 혼합형의 주소를 반환하여 값 형식을 CLR 힙에 배치해야 합니다. 이 CLR 힙에서는 값 형식의 boxing 이미지가 생성됩니다.  예를 들어 다음과 같은 C\# 코드가 있습니다.  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 이 코드는 겉보기에 매우 단순하지만 실제로는 복잡한 과정을 내포하고 있습니다.  C\#은 드러나지 않은 채 진행되는 작업의 복잡한 내용과 boxing 자체의 추상적인 내용을 숨기도록 디자인되었습니다.  하지만 Managed Extensions for C\+\+에서는 이 방법이 효율성 측면에서 잘못된 판단을 가져올 수 있으므로 사용자가 직접 명시적으로 지정하도록 합니다.  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 boxing이 암시적입니다.  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 `__box` 키워드는 Managed Extensions에서 매우 중요하게 사용되지만 C\# 및 [!INCLUDE[vbprvb](../Token/vbprvb_md.md)] 등의 언어는 이 키워드를 사용하지 않도록 디자인되었습니다. 이러한 언어에서는 관리되는 힙의 boxed 인스턴스를 직접 조작하는 구문 및 추적 핸들이 제공됩니다.  예를 들어, 다음과 같은 작은 프로그램을 생각해 볼 수 있습니다.  
  
```  
int main() {  
   double result = 3.14159;  
   __box double * br = __box( result );  
  
   result = 2.7;   
   *br = 2.17;     
   Object * o = br;  
  
   Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
   Console::WriteLine( S"result :: {0}", __box(result) ) ;  
   Console::WriteLine( S"result :: {0}", br );  
}  
```  
  
 `WriteLine`의 세 가지 호출에 대해 생성되는 기본 코드는 boxed 값 형식의 값에 액세스하기 위해 치러야 할 여러 가지 대가를 보여 줍니다. 이러한 차이를 지적해 주신 분은 Yves Dolce입니다. 여기서 표시된 줄은 각 호출과 관련된 오버헤드를 표시합니다.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
call       void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", __box(result) ) ;  
Ldstr    " result :: {0}"  
ldloc.0  
box    [mscorlib]System.Double // box overhead  
call    void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", br );  
ldstr    "result :: {0}"  
ldloc.0  
call     void [mscorlib]System.Console::WriteLine(string, object)  
```  
  
 boxed 값 형식을 `Console::WriteLine`에 직접 전달하면 `ToString()`을 호출하거나 boxing할 필요가 없습니다. 물론 이전의 boxing에서 `br`를 초기화하므로 `br`를 실제로 사용하지 않으면 어떠한 이점도 없습니다.  
  
 새 구문에서 boxed 값 형식을 지원하는 것은 형식 시스템 내에서 그 성능을 유지하면서도 훨씬 더 자연스럽게 통합할 수 있는 방법입니다.  예를 들어, 위의 작은 프로그램을 다음과 같이 변환할 수 있습니다.  
  
```  
int main()  
{  
   double result = 3.14159;  
   double^ br = result;  
   result = 2.7;  
   *br = 2.17;  
   Object^ o = br;  
   Console::WriteLine( "result :: {0}", result.ToString() );  
   Console::WriteLine( "result :: {0}", result );  
   Console::WriteLine( "result :: {0}", br );  
}  
```  
  
## 참고 항목  
 [값 형식 및 동작\(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [방법: 명시적으로 boxing 요청](../dotnet/how-to-explicitly-request-boxing.md)