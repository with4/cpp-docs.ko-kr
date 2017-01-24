---
title: "방법: 어셈블리 호환성 문제 진단 및 해결(C++/CLI) | Microsoft Docs"
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
  - "호환성, 어셈블리 간"
  - "예외, 부적절한 동작 진단"
  - "버전 관리"
  - "버전 관리, 충돌 진단"
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 어셈블리 호환성 문제 진단 및 해결(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 컴파일 타임에 참조한 어셈블리의 버전이 런타임에 참조한 어셈블리의 버전과 일치하지 않는 경우 발생하는 결과 및 이와 관련된 문제를 방지하는 방법에 대해 설명합니다.  
  
 어셈블리를 컴파일할 때 `#using` 구문을 사용하여 다른 어셈블리를 참조할 수 있습니다.  컴파일 과정에서 컴파일러는 이러한 어셈블리에 액세스합니다.  이러한 어셈블리의 정보는 최적화 분석을 내리는 데 사용됩니다.  
  
 그러나 참조되는 어셈블리가 변경되어 이를 다시 컴파일하는 경우 이 어셈블리에 종속된 참조하는 어셈블리를 다시 컴파일하지 않으면 어셈블리가 계속 호환되지 않을 수 있습니다.  처음에는 유효했던 최적화 분석이 새 어셈블리 버전에서는 올바르지 않을 수 있습니다.  이와 같이 어셈블리가 불일치하면 여러 가지 런타임 오류가 발생할 수 있습니다.  이 경우 어떠한 특별한 예외도 생성되지 않습니다.  런타임에 오류가 보고되는 방식은 문제의 원인이 된 코드 변경의 성격에 따라 다릅니다.  
  
 제품의 릴리스 버전에 대해 응용 프로그램 전체를 다시 빌드하는 한 최종 프로덕션 코드에서는 이러한 오류가 발생하지 않습니다.  공개적으로 릴리스되는 어셈블리에는 공식 버전 번호를 부여하여 이러한 문제가 발생하지 않도록 해야 합니다.  자세한 내용은 [어셈블리 버전 관리](../Topic/Assembly%20Versioning.md)을 참조하십시오.  
  
### 비호환성 오류 진단 및 해결  
  
1.  다른 어셈블리를 참조하는 코드에서 런타임 예외나 기타 오류 조건이 발생했지만 특별한 원인이 없다면 오래된 어셈블리를 처리해야 할 수도 있습니다.  
  
2.  우선 예외나 기타 오류 조건을 격리하여 재현합니다.  어셈블리가 오래되어 문제가 발생하는 것이라면 동일한 문제가 재현되어야 합니다.  
  
3.  응용 프로그램에서 참조하고 있는 모든 어셈블리의 타임스탬프를 확인합니다.  
  
4.  참조되는 어셈블리의 타임스탬프가 하나라도 응용 프로그램의 마지막 컴파일 시점보다 최근 것이라면 응용 프로그램이 오래된 것입니다.  이 경우 가장 최근의 어셈블리를 사용하여 응용 프로그램을 다시 컴파일하고 코드의 필요한 부분을 변경합니다.  
  
5.  응용 프로그램을 다시 실행하고 문제를 재현하는 데 수행했던 과정을 반복한 다음 예외가 발생하는지 여부를 확인합니다.  
  
## 예제  
 다음 프로그램에서는 메서드의 액세스 가능성을 축소했지만 이를 다시 컴파일하지 않은 채 다른 어셈블리에서 이 메서드에 액세스하려고 하는 경우 발생하는 문제를 보여 줍니다.  먼저 `changeaccess.cpp`를 컴파일합니다.  이는 변경될 참조 어셈블리입니다.  그런 다음 `referencing.cpp`를 컴파일합니다.  이 경우 컴파일에 성공합니다.  이제 호출되는 메서드의 액세스 가능성을 축소합니다.  `/DCHANGE_ACCESS` 플래그를 사용하여 `changeaccess.cpp`를 다시 컴파일합니다.  이렇게 하면 전용 메서드가 보호되는 메서드로 변경되므로 올바르게 호출할 수 없습니다.  `referencing.exe`를 다시 컴파일하지 말고 응용 프로그램을 재실행합니다.  <xref:System.MethodAccessException> 예외가 발생합니다.  
  
```  
// changeaccess.cpp  
// compile with: /clr:safe /LD  
// After the initial compilation, add /DCHANGE_ACCESS and rerun  
// referencing.exe to introduce an error at runtime. To correct  
// the problem, recompile referencing.exe  
  
public ref class Test {  
#if defined(CHANGE_ACCESS)  
protected:  
#else  
public:  
#endif  
  
  int access_me() {  
    return 0;  
  }  
  
};  
  
```  
  
```  
// referencing.cpp  
// compile with: /clr:safe   
#using <changeaccess.dll>  
  
// Force the function to be inline, to override the compiler's own  
// algorithm.  
__forceinline  
int CallMethod(Test^ t) {  
  // The call is allowed only if access_me is declared public  
  return t->access_me();  
}  
  
int main() {  
  Test^ t = gcnew Test();  
  try  
  {  
    CallMethod(t);  
    System::Console::WriteLine("No exception.");  
  }  
  catch (System::Exception ^ e)  
  {  
    System::Console::WriteLine("Exception!");  
  }  
  return 0;  
}  
  
```  
  
## 참고 항목  
 [\#using 지시문](../preprocessor/hash-using-directive-cpp.md)   
 [관리되는 형식](../dotnet/managed-types-cpp-cli.md)