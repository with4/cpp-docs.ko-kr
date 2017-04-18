---
title: "컴파일러 경고 (수준 3) C4635 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d4c85ca32903e20ea18a731872c25ee999b67f89
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4635"></a>컴파일러 경고(수준 3) C4635
XML 문서 주석 대상: 잘못된 형식의 XML: 이유  
  
 컴파일러가 XML 태그에서 일부 문제를 발견했습니다.  문제를 수정하고 다시 컴파일합니다.  
  
 다음 샘플에서는 C4635를 생성합니다.  
  
```  
// C4635.cpp  
// compile with: /doc /clr /W3 /c  
/// <summary>     
/// The contents of the folder have changed.  
/// <summary/>   // C4635  
  
// try the following line instead  
// /// </summary>  
public ref class Test {};  
```  
  
 이 샘플은 **끝 태그 'member'가 시작 태그 'summary'와 일치하지 않습니다**를 출력합니다.  
  
 이 샘플의 문제는 끝 태그에 \<요약 > 잘못 구성 되어 컴파일러가 인식 하지 못하는 \<요약 > 끝 태그입니다.  \<멤버 > 모든 /doc 컴파일에서 컴파일러가.xdc 파일에 태그를 포함 합니다.  따라서 문제는 끝 태그 \</member >, 컴파일러가 처리 한 이전의 시작 태그와 일치 하지 않습니다 (\<요약 >.
