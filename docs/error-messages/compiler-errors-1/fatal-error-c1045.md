---
title: "심각한 오류 C1045 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1045
dev_langs:
- C++
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: 7
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
ms.openlocfilehash: e2e060465ffca50b116aa7a7020d9e1bdda8f2de
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1045"></a>심각한 오류 C1045
컴파일러 한계 : 링크 사양이 너무 많이 중첩되었습니다.  
  
 중첩된 외부 참조가 컴파일러 한계를 초과했습니다. 중첩된 외부 참조는 `extern` "C++"와 같은 외부 링크 형식에서 사용할 수 있습니다. 오류를 해결하려면 중첩된 외부 참조 수를 줄입니다.
