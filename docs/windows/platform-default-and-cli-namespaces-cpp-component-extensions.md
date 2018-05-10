---
title: 플랫폼, default 및 cli 네임 스페이스 (c + + 구성 요소 확장명) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- lang
- cli
dev_langs:
- C++
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b466a94aba9f19907a5438a8b8e623d65aa0ac2d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="platform-default-and-cli-namespaces--c-component-extensions"></a>Platform, default 및 cli 네임스페이스(C++ 구성 요소 확장)
네임스페이스는 언어 요소의 이름을 한정하므로, 이름이 그렇지 않았다면 소스 코드의 다른 곳에 있는 같은 이름과 충돌하지 않습니다. 예를 들어 이름 충돌이 못하게 컴파일러에서 인식 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)합니다. 네임스페이스는 컴파일러에 의해 사용되지만 컴파일된 어셈블리에 유지되지 않습니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 Visual C++는 프로젝트를 만들 때 프로젝트에 대한 기본 네임스페이스를 제공합니다. 수동으로 Windows Runtime에서.winmd 파일의 이름을 루트 네임 스페이스의 이름과 일치 해야 하지만 네임 스페이스를 바꿀 수 있습니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 자세한 내용은 참조 [네임 스페이스 및 형식 표시 유형 (C + + /cli CX)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **구문**  
  
```  
using namespace cli;  
```  
  
 **주의**  
  
 C + + /cli CLI 지원는 `cli` 네임 스페이스입니다. 로 컴파일할 때 **/clr**, `using` 구문 섹션에는 문이 포함 됩니다.  
  
 다음 언어 기능은 `cli` 네임스페이스에 있습니다.  
  
-   [배열](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior_ptr(C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin_ptr(C++/CLI)](../windows/pin-ptr-cpp-cli.md)  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 `cli` 네임스페이스의 기호를 코드의 사용자 정의 기호로 사용할 수 있음을 보여 줍니다.  그러나 그와 같이 할 경우 같은 이름의 `cli` 언어 요소에 대한 참조를 명시적 또는 묵시적으로 한정해야 합니다.  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)