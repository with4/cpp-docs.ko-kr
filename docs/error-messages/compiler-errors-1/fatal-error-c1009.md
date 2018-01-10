---
title: "심각한 오류 C1009 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1009
dev_langs: C++
helpviewer_keywords: C1009
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92d91240ea092ff75387246952ce5b7207527173
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1009"></a>심각한 오류 C1009
컴파일러 한계: 매크로가 너무 많이 중첩  
  
 컴파일러는 동시에 너무 많은 매크로 확장 하 려 했습니다. 컴파일러의 한 제한은 256 수준의 중첩된 매크로입니다. 중첩 된 매크로 보다 간단한 매크로로 분할 합니다.