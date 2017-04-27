---
title: "추출 연산자 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- extraction operators
- '>> operator, extraction operators'
- operators [C++], extraction
f1_keywords: []
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: e5dcc1e57b807ee7ff7b4292f31563d4041c0bdd
ms.lasthandoff: 02/24/2017

---
# <a name="using-extraction-operators"></a>추출 연산자 사용
모든 표준 C++ 데이터 형식용으로 프로그래밍된 추출 연산자(`>>`)를 사용하면 입력 스트림 개체에서 바이트를 가장 쉽게 가져올 수 있습니다.  
  
 서식 있는 텍스트 입력 추출 연산자는 공백을 사용하여 들어오는 데이터 값을 구분합니다. 텍스트 필드에 단어가 여러 개 있거나 숫자가 쉼표로 구분되는 경우에는 이러한 방식이 불편합니다. 이러한 경우에 대신 사용할 수 있는 방법 중 하나는 서식 없는 입력 구성원 함수 [istream::getline](../standard-library/basic-istream-class.md#basic_istream__getline)을 사용하여 공백이 포함된 텍스트 블록을 읽은 다음 특수 함수로 해당 블록을 구문 분석하는 것입니다. istream 구성원를 호출하여 문자 데이터를 추출하고 서식을 지정할 수 있는 `GetNextToken` 등의 구성원 함수를 사용하여 입력 스트림 클래스를 파생할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [입력 스트림](../standard-library/input-streams.md)


