---
title: "컴파일러 경고 (수준 1) C4910 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b8416e456a7d985eb7a3c40addb716ba5c30bf96
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4910"></a>컴파일러 경고(수준 1) C4910
'\<식별자 > ': '__declspec (dllexport)' 및 'extern' 명시적 인스턴스화에서 호환 되지 않습니다.  
  
 라는 명시적 템플릿 인스턴스화가 *\<식별자 >* 둘 다로 수정 된 `__declspec(dllexport)` 및 `extern` 키워드입니다. 그러나 이러한 키워드는 함께 사용할 수 없습니다. `__declspec(dllexport)` 키워드는 템플릿 클래스의 인스턴스화를 의미하는 반면, `extern` 키워드는 템플릿 클래스를 자동으로 인스턴스화하지 않음을 의미합니다.  
  
## <a name="see-also"></a>참고 항목  
 [명시적 인스턴스화](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [일반 규칙 및 제한 사항](../../cpp/general-rules-and-limitations.md)
