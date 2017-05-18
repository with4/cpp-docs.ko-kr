---
title: "링커 도구 경고 LNK4227 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ee566318c7d19159f9a2c084d348b5010a65e2de
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4227"></a>링커 도구 경고 LNK4227
메타 데이터 작업 경고 (HRESULT): warning_message  
  
링커가 병합할 때 메타 데이터 차이 발견 했습니다.  
  
-   현재 구축 중인 어셈블리와 하나 이상의 참조 된 어셈블리입니다.  
  
-   하나 이상의 소스 코드 파일을 컴파일입니다.  
  
예를 들어 LNK4227 원인은 두 전역 함수의 이름이 같지만 다르게 선언 된 매개 변수 정보를 설정한 경우 (선언 모든 컴파일 대상에 일치 하지 않습니다.). /TEXT ildasm.exe를 사용 하 여 /METADATA `object_file` 각.obj 파일을 표시 형식을 어떻게 다른 지 합니다.  
  
또한 LNK4227 다른 도구로 인해 발생 하는 문제를 보고 합니다. 예를 들어 al.exe; 참조 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)합니다.  
  
경고를 해결 하는 메타 데이터 문제를 해결 해야만 합니다.  
  
예를 들어 LNK4227 참조 된 어셈블리가 참조 하는 어셈블리와 다르게 서명 하는 경우 생성 됩니다.  
  
다음 샘플에서는 LNK4227 오류가 생성 됩니다.  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 한 다음,  
  
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
  
LNK4227 잘못 된 형식으로 버전 번호는 어셈블리 특성에 전달 되는 경우에 생성할 수 있습니다.  ' *' 표기법은 AssemblyVersionAttribute에만 적용 됩니다.  이 경고를 해결 하려면 숫자만 AssemblyVersionAttribute 이외의 버전 특성에 사용 합니다.  
  
다음 샘플에서는 LNK4227 오류가 생성 됩니다.  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```
