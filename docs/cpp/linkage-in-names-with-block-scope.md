---
title: 블록 범위가 있는 이름의 링크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- block scope [C++]
- external linkage, scope linkage rules
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab7758e962c028c4746836e470ee43eaab510f9e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418889"
---
# <a name="linkage-in-names-with-block-scope"></a>블록 범위가 있는 이름의 링크
다음 링크 규칙이 블록 범위가 있는 이름(로컬 이름)에 적용됩니다.  
  
-   로 선언 된 이름은 `extern` 로 이전에 선언 된 경우가 아니면 외부 링크가 있는 **정적**합니다.  
  
-   블록 범위가 있는 다른 모든 이름에는 링크가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)