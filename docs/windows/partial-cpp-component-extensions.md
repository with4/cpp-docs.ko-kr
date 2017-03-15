---
title: "partial(C++ 구성 요소 확장) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "partial_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial"
  - "C++/CX,partial"
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# partial(C++ 구성 요소 확장)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`partial` 키워드를 사용하면 동일한 ref 클래스의 다른 부분이 개별적으로 다른 파일에서 인증되도록 할 수 있습니다.  
  
## 모든 런타임  
 \(이 언어 기능은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에만 적용됩니다.\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 두 개의 부분 정의가 있는 ref 클래스의 경우, `partial` 키워드가 첫 번째 정의에 적용되고 일반적으로 자동 생성 코드에 의해 수행되므로 사람이 직접 키워드를 사용하는 경우는 드뭅니다.  클래스의 모든 후속 부분 정의의 경우 *class\-key* 키워드와 클래스 식별자에서 `partial` 한정자를 생략합니다.  컴파일러가 이전에 정의된 ref 클래스와 클래스 식별자를 만나지만 `partial` 키워드가 없으면 내부적으로 ref 클래스 정의의 모든 부분을 하나의 정의로 결합합니다.  
  
### 구문  
  
```cpp  
  
partial class-key identifier {  
   /* The first part of the partial class definition. This is typically auto-generated*/  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same identifier is specified, but the "partial" keyword is omitted. */  
}  
  
```  
  
### 매개 변수  
 *class\-key*  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서 지원되는 클래스 또는 구조체를 선언하는 키워드입니다.  `ref class`, `value class`, `ref struct` 또는 `value struct`입니다.  
  
 *identifier*  
 정의된 형식의 이름입니다.  
  
### 설명  
 partial 클래스를 사용하면 사용자가 한 파일의 클래스 정의에서 한 부분을 수정하고 자동 코드 생성 소프트웨어\(예: XAML 디자이너\)가 다른 파일에서 동일한 클래스의 코드를 수정하는 시나리오가 가능합니다.  partial 클래스를 사용하면 자동 코드 생성기가 코드를 덮어쓰지 않게 할 수 있습니다.  Visual Studio 프로젝트에서는 생성된 파일에 `partial` 한정자가 자동으로 적용됩니다.  
  
 내용: 두 가지 예외 항목을 제외하고, partial 클래스 정의는 `partial` 키워드를 생략할 경우 전체 클래스 정의에 포함할 수 있는 모든 항목을 포함할 수 있습니다.  그러나 클래스 액세스 가능성\(예: `public partial class X {…};`\) 또는 `declspec`을 지정할 수 없습니다.  
  
 *identifier*의 partial 클래스 정의에 사용되는 액세스 지정자는 *identifier*의 후속 부분 또는 전체 클래스 정의의 기본 액세스 가능성에 영향을 미치지 않습니다.  정적 데이터 멤버의 인라인 정의가 허용됩니다.  
  
 선언: 클래스 *identifier*의 부분 정의에서는 이름 *identifier*만 지정하지만, *identifier*는 클래스 정의를 요구하는 방식으로 사용할 수 없습니다.  이름 *identifier*는 컴파일러가 *identifier*의 전체 정의를 만날 때까지 *identifier*의 크기를 파악하거나 *identifier*의 베이스나 멤버를 이용하는 데 사용할 수 없습니다.  
  
 개수와 순서: *identifier*에 대한 0개 이상의 partial 클래스가 있을 수 있습니다.  *identifier*의 모든 partial 클래스 정의는 *identifier*의 하나의 완전한 정의보다 구문적으로 앞에 나와야 하지만\(전체 정의가 있는 경우, 그렇지 않을 경우 전방 선언된 것처럼 사용하는 경우를 제외하고 클래스를 사용할 수 없음\) *identifier*의 전방 선언보다 앞에 나올 필요는 없습니다.  모든 클래스\-키가 일치해야 합니다.  
  
 전체 정의: 클래스 *identifier*의 전체 정의 지점에서는 *identifier* 정의가 모든 기본 클래스, 멤버 등을 partial 클래스에서 발견되고 정의된 순서대로 선언한 것처럼 동작이 동일합니다.  
  
 템플릿: partial 클래스는 템플릿이 될 수 없습니다.  
  
 제네릭: 전체 정의가 일반이 될 수 있는 경우 partial 클래스가 제네릭이 될 수 있습니다.  하지만 모든 부분 및 전체 클래스는 형식 매개 변수 이름을 포함하여 정확히 동일한 제네릭 매개 변수를 가져야 합니다.  
  
 `partial`  키워드를 사용하는 방법에 대한 자세한 내용을 보려면 [Partial 클래스 \(C \+ \+ CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023)을 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 \(이 언어 기능은 공용 언어 런타임에는 적용되지 않습니다.\)  
  
## 참고 항목  
 [Partial 클래스\(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023)