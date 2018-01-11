---
title: "심각한 오류 C1045 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1045
dev_langs: C++
helpviewer_keywords: C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce780ee4f9299f9e5fd72e101115fc055d0f5920
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1045"></a>심각한 오류 C1045
컴파일러 한계 : 링크 사양이 너무 많이 중첩되었습니다.  
  
 중첩된 외부 참조가 컴파일러 한계를 초과했습니다. 중첩된 외부 참조는 `extern` "C++"와 같은 외부 링크 형식에서 사용할 수 있습니다. 오류를 해결하려면 중첩된 외부 참조 수를 줄입니다.