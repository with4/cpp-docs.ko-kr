---
title: "C++ 클래스에서 dllimport 및 dllexport 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스[C++], 선언"
  - "클래스[C++], 내보내기 가능하며 상속인"
  - "선언[C++], class"
  - "클래스 선언"
  - "dllexport 특성[C++]"
  - "dllexport 특성[C++], 클래스"
  - "dllimport 특성[C++], 클래스"
  - "내보내기가 가능한 클래스[C++]"
  - "클래스 내보내기"
  - "상속[C++], 내보내기가 가능한 클래스"
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 클래스에서 dllimport 및 dllexport 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 **dllimport** 또는 `dllexport` 특성을 사용하여 C\+\+ 클래스를 선언할 수 있습니다.  이 폼은 전체 클래스를 가져오거나 내보냄을 의미합니다.  이 방법으로 내보낸 클래스를 내보낼 수 있는 클래스라고 합니다.  
  
 다음 예제에서는 내보낼 수 있는 클래스를 정의합니다.  모든 멤버 함수 및 정적 데이터를 내보냅니다.  
  
```  
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 내보낼 수 있는 클래스의 멤버에 대해 **dllimport** 및 `dllexport` 특성을 명시적으로 사용할 수 없습니다.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a> dllexport 클래스  
 `dllexport` 클래스를 선언할 때 모든 멤버 함수와 정적 데이터 멤버를 내보냅니다.  모든 해당 멤버의 정의를 동일한 프로그램에 제공해야 합니다.  그렇게 하지 않으면 링커 오류가 생성됩니다.  명시적 정의를 제공할 필요가 없는 순수 가상 함수에 이 규칙에 대한 예외가 적용됩니다.  그러나 추상 클래스에 대한 소멸자가 항상 기본 클래스의 소멸자에 의해 호출되므로 순수 가상 소멸자는 항상 정의를 제공해야 합니다.  이 규칙은 내보내기 불가능한 클래스에 대해서도 동일합니다.  
  
 클래스를 반환하는 함수 또는 클래스 형식의 데이터를 내보낼 경우 클래스를 내보내야 합니다.  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a> dllimport 클래스  
 **dllimport** 클래스를 선언할 때 모든 멤버 함수 및 정적 데이터 멤버를 가져옵니다.  비클래스 형식에서 **dllimport** 및 `dllexport`의 동작과 달리 정적 데이터 멤버는 **dllimport** 클래스가 정의된 프로그램에서 정의를 지정할 수 없습니다.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a> 상속 및 내보내기 가능 클래스  
 내보낼 수 있는 클래스의 모든 기본 클래스는 내보낼 수 있어야 합니다.  그렇지 않으면 컴파일러 경고가 생성됩니다.  또한 클래스이기도 한 액세스 가능 멤버를 모두 내보낼 수 있어야 합니다.  이 규칙에 의해 `dllexport` 클래스가 **dllimport** 클래스에서 상속하고 **dllimport** 클래스가 `dllexport` 클래스에서 상속할 수 있습니다\(후자는 권장되지 않음\).  따라서 C\+\+ 액세스 규칙에 따라 DLL의 클라이언트에 액세스할 수 있는 모든 항목은 내보낼 수 있는 인터페이스의 일부여야 합니다.  인라인 함수에서 참조되는 전용 데이터 멤버가 여기에 포함됩니다.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a> 선택적 멤버 가져오기\/내보내기  
 클래스의 멤버 함수와 정적 데이터에는 암시적으로 외부 링크가 있으므로 전체 클래스를 내보내지 않는 한 **dllimport** 또는 `dllexport` 특성을 사용하여 선언할 수 있습니다.  전체 클래스를 가져오거나 내보내는 경우 멤버 함수와 데이터를 **dllimport** 또는 `dllexport`로 명시적으로 선언할 수 없습니다.  클래스 정의 안에 정적 데이터 멤버를 `dllexport`로 선언할 경우 비클래스 외부 링크와 동일한 프로그램 안에 정의가 발생해야 합니다.  
  
 마찬가지로 **dllimport** 또는 `dllexport` 특성을 사용하여 멤버 함수를 선언할 수 있습니다.  이 경우 같은 프로그램 안에 `dllexport` 정의를 제공해야 합니다.  
  
 선택적 멤버 가져오기 및 내보내기와 관련하여 몇 가지 중요한 사항을 기억하십시오.  
  
-   선택적 멤버 가져오기\/내보내기는 더 제한적으로 내보낸 클래스 인터페이스의 버전을 제공하는 데 주로 사용됩니다. 즉, 언어가 허용하는 것보다 적게 공개 및 전용 기능을 노출하는 DLL을 디자인할 수 있습니다.  내보낼 수 있는 인터페이스를 자세히 조정하는 데에도 유용합니다. 정의에 따라 클라이언트가 일부 전용 데이터에 액세스할 수 없는 경우 전체 클래스를 내보낼 필요가 없습니다.  
  
-   클래스의 가상 함수 한 개를 내보내는 경우 가상 함수를 모두 내보내거나 적어도 클라이언트가 직접 사용할 수 있는 버전을 제공해야 합니다.  
  
-   선택적 멤버 가져오기\/내보내기가 가상 함수와 함께 사용되는 클래스가 있을 경우 함수가 내보내기 가능 인터페이스에 있거나 인라인으로 정의되어야 합니다\(클라이언트가 볼 수 있음\).  
  
-   멤버를 `dllexport`로 정의하고 클래스 정의에 포함하지 않을 경우 컴파일러 오류가 생성됩니다.  클래스 헤더에 멤버를 정의해야 합니다.  
  
-   클래스 멤버를 **dllimport** 또는 `dllexport`로 정의할 수 있지만 클래스 정의에 지정된 인터페이스를 재정의할 수는 없습니다.  
  
-   멤버 함수를 선언한 클래스 정의 본문이 아닌 다른 위치에 멤버 함수를 정의할 경우 함수가 `dllexport` 또는 **dllimport**로 정의되고 이 정의가 클래스 선언에 지정된 정의와 다르면 경고가 생성됩니다.  
  
### Microsoft 전용 종료  
  
## 참고 항목  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)