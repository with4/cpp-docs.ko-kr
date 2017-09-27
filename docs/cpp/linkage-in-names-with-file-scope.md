---
title: "파일 범위가 있는 이름의 링크 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- static modifier, file scope
- static names and file scope
- file scope [C++]
- declarations [C++], external
- external linkage, scope linkage rules
- static variables, external declarations
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c4d33071426eac428cc1728aa13b403953a99389
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-file-scope"></a>파일 범위가 있는 이름의 링크
다음 링크 규칙이 파일 범위가 있는 이름(`typedef` 및 열거자 이름 제외)에 적용됩니다.  
  
-   이름으로 명시적으로 선언 되 면 **정적**, 내부 링크가 있으며 자체 변환 단위 내부의 프로그램 요소가 식별 합니다.  
  
-   열거자 이름 및 `typedef` 이름에는 링크가 없습니다.  
  
-   파일 범위가 있는 다른 모든 이름에는 외부 링크가 있습니다.  
  
 **Microsoft 전용**  
  
-   파일 범위가 있는 함수 이름을 명시적으로 선언 된 경우 **인라인**, 인스턴스화된 나 해당 주소를 참조 하는 경우 외부 링크를 포함 합니다. 따라서 파일 범위가 있는 함수는 내부 또는 외부 링크를 가질 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
 클래스가 내부 링크를 가지는 경우는 다음과 같습니다.  
  
-   예를 들어 멤버 액세스 제어, 멤버 함수, 생성자, 소멸자 등의 C++ 기능을 사용하지 않습니다.  
  
-   외부 링크가 있는 다른 이름 선언에 사용되지 않습니다. 이 제한은 외부 연결을 가진 함수에 클래스 형식의 개체가 전달될 경우 클래스가 외부 연결을 가질 수 있도록 한다는 것을 의미합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)
