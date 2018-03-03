---
title: "방법: 어셈블리 호환성 문제 진단 및 해결 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a175705bd5d303187a11bf3e7779669a3a30e483
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-diagnose-and-fix-assembly-compatibility-problems-ccli"></a>방법: 어셈블리 호환성 문제 진단 및 해결(C++/CLI)
이 항목에서는 컴파일 타임에 참조 하는 어셈블리의 버전 런타임 시 참조 된 어셈블리의 버전과 일치 하지 않는 경우 발생할 수 있는 결과 설명 하 고 문제를 방지 하는 방법입니다.  
  
 어셈블리를 컴파일할 때 다른 어셈블리를 참조할 수 있습니다는 `#using` 구문입니다. 컴파일하는 동안 이러한 어셈블리는 컴파일러에 의해 액세스 됩니다. 이러한 어셈블리의 정보를 사용 하 여 최적화 결정을 내릴 수 있습니다.  
  
 그러나 참조 된 어셈블리를 변경 하 고 다시 컴파일하면을 참조 하는 것에 종속 된 어셈블리를 컴파일하지 않으면 어셈블리 않을 수도 있습니다 여전히 호환 되어야 합니다. 유효 했던 최적화 분석이 먼저 올바르지 않을 수 새 어셈블리 버전을 기준으로 합니다. 이러한 비 호환성으로 인해 다양 한 런타임 오류가 발생할 수 있습니다. 이러한 경우 링커에 특정 예외가 없습니다. 런타임에 실패는 보고 하는 방법은 문제를 발생 시킨 코드 변경의 특성에 따라 달라 집니다.  
  
 이러한 오류는 제품의 릴리스 버전에 대 한 전체 응용 프로그램이 빌드될으로 최종 프로덕션 코드에 문제가 되지 않아야 합니다. 공개적으로 출시 하는 어셈블리를 이러한 문제가 발생 하지 않으며 공식 버전 번호로 표시 되어야 합니다. 자세한 내용은 [어셈블리 버전 관리](/dotnet/framework/app-domains/assembly-versioning)를 참조하세요.  
  
### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>진단 및 비 호환성 오류를 해결 합니다.  
  
1.  런타임 예외 나 다른 어셈블리를 참조 하는 코드에서 발생 하는 기타 오류 조건 식별 된 다른 원인이 있을 경우 최신 어셈블리로 처리 해야 할 수도 있습니다.  
  
2.  첫째, 격리 하 고 또는 기타 오류 조건 예외를 재현 합니다. 오래 된 예외로 인해 발생 하는 문제를 재현할 수 여야 합니다.  
  
3.  응용 프로그램에서 참조 되는 모든 어셈블리의 타임 스탬프를 확인 합니다.  
  
4.  모든 참조 된 어셈블리의 타임 스탬프를 응용 프로그램의 마지막 컴파일 타임 스탬프 보다 최신인 응용 프로그램 만료 되었습니다. 이 경우 응용 프로그램을 가장 최근의 어셈블리를 다시 컴파일하고 필요한 코드 변경을 수행 합니다.  
  
5.  응용 프로그램을 다시 실행 하 고 문제를 재현 하는 예외가 발생 하지 않으면 확인 하는 단계를 수행 하십시오.  
  
## <a name="example"></a>예  
 다음 프로그램 메서드의 액세스 가능성을 축소 하 고 다시 컴파일할 필요 없이 다른 어셈블리에서이 메서드에 액세스 하 여 문제를 보여 줍니다. 컴파일 해 보십시오. `changeaccess.cpp` 첫 번째입니다. 이것이 변경 하는 참조 된 어셈블리입니다. 그런 다음 컴파일합니다 `referencing.cpp`합니다. 컴파일이 성공합니다. 이제 호출 된 메서드의 액세스 가능성을 줄입니다. Recompile `changeaccess.cpp` 플래그로 `/DCHANGE_ACCESS`합니다. 이렇게 하면 메서드가 protected 보다는 private, 호출 수 있도록 더 이상 수 합법적으로 합니다. 다시 컴파일하지 않고 `referencing.exe`, 응용 프로그램을 다시 실행 합니다. 예외가 <xref:System.MethodAccessException> 발생 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [#using 지시문](../preprocessor/hash-using-directive-cpp.md)   
 [관리되는 형식(C++/CLI)](../dotnet/managed-types-cpp-cli.md)