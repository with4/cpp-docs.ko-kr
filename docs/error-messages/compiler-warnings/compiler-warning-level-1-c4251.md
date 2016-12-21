---
title: "컴파일러 경고 (수준 1) C4251 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4251"
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : class 'type'에서는 class 'type2'의 클라이언트에서 DLL 인터페이스를 사용하도록 지정해야 합니다.  
  
 [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md)을 사용하여 클래스를 내보낼 때 데이터가 손상될 가능성을 최소화하려면 다음 사항을 확인해야 합니다.  
  
-   DLL에서 내보낸 함수를 통해 모든 정적 데이터에 액세스할 수 있어야 합니다.  
  
-   클래스의 인라인 메서드로 정적 데이터를 수정할 수 없어야 합니다.  
  
-   클래스의 인라인 메서드에서 CRT 함수를 사용하지 말아야 하거나 다른 라이브러리 함수에서 정적 데이터를 사용해야 합니다. 자세한 내용은 [DLL 경계를 넘어 CRT 개체를 전달할 때 발생할 수 있는 오류](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)를 참조하십시오.  
  
-   EXE와 DLL 인스턴스화의 정적 데이터가 서로 다른 형식은 인라인 여부와 상관없이 클래스의 어떠한 메서드에서도 사용할 수 없어야 합니다.  
  
 해당 형식의 개체를 인스턴스화하고 삭제하기 위해 호출할 수 있는 함수 및 가상 함수가 있는 클래스를 정의하는 DLL을 정의하면 클래스를 내보내지 않을 수 있습니다.  그런 다음 해당 형식에 대해 가상 함수를 호출하기만 하면 됩니다.  
  
 템플릿 내보내기에 대한 자세한 내용은 참조 하십시오. [http:\/\/support.microsoft.com\/default.aspx?scid\=KB;EN\-US;168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 표준 C\+\+ 라이브러리에서 형식을 파생하고, 디버그 릴리스\(**\/MTd**\)를 컴파일하고, 컴파일러 오류 메시지에서 \_Container\_base를 참조하는 경우 C4251이 무시될 수 있습니다.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```