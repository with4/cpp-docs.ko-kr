---
title: __identifier (C + + /cli CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4d68d21fc9436bff0e39fa474b97ec54138e15b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="identifier-ccli"></a>__identifier(C++/CLI)
식별자로 Visual c + + 키워드를 사용 하도록 설정 합니다.  
  
## <a name="all-platforms"></a>모든 플랫폼  
**구문**  
  
```  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
**주의**  
  
사용은 `__identifier` 키워드가 아닌 식별자에 대 한 키워드는 허용 되지 않지만 스타일 문제도 좋습니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 예제에서는 클래스 이름이 `template` C#에서 만들어진 및 DLL로 분산 됩니다. 사용 하는 Visual c + + 프로그램에서는 `template` 클래스는 `__identifier` 키워드는 팩트를 숨깁니다는 `template` 는 표준 c + + 키워드입니다.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **주의**  
  
 `__identifier` 키워드는 사용할 수는 **/clr** 컴파일러 옵션입니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 예제에서는 클래스 이름이 `template` C#에서 만들어진 및 DLL로 분산 됩니다. 사용 하는 Visual c + + 프로그램에서는 `template` 클래스는 `__identifier` 키워드는 팩트를 숨깁니다는 `template` 는 표준 c + + 키워드입니다.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼의 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)   
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)