---
title: "컴파일러 오류 C3552 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3552
dev_langs: C++
helpviewer_keywords: C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 54526c39a928cc534ba815ef8fda802db85f4020
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3552"></a>컴파일러 오류 C3552
'typename': 컴파일하면 지정되는 반환 형식은 'auto'를 포함할 수 없습니다.  
  
 `auto` 키워드를 함수 반환 형식에 대한 자리 표시자로 사용하는 경우 컴파일하면 지정되는 반환 형식을 제공해야 합니다. 그러나 다른 `auto` 키워드를 사용하여 컴파일하면 지정되는 반환 형식을 지정할 수는 없습니다. 예를 들어 다음 코드 조각은 C3552 오류를 생성합니다.  
  
 `auto myFunction->auto; // C3552`