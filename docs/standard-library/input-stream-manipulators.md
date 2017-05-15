---
title: "입력 스트림 조작자 | Microsoft 문서"
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
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 3b5f43364e0cfb286ead62f1c38d4d30aec707fc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="input-stream-manipulators"></a>입력 스트림 조작자
[setprecision]--brokenlink--(../Topic/not%20found:3ddde610-70cc-4cfa-8a89-3e83d1d356a8.md#setprecision) 같은 많은 조작자가 `ios` 클래스에 대해 정의되어 입력 스트림에 적용됩니다. 그러나 실제로 입력 스트림 개체에 영향을 주는 조작자는 거의 없습니다. 이러한 조작자 중에서 기수 조작자인 `dec`, `oct` 및 `hex`가 가장 중요하며, 입력 스트림에서 숫자에 사용된 변환 기준을 결정합니다.  
  
 추출 시 `hex` 조작자를 사용하여 다양한 입력 형식을 처리할 수 있습니다. 예를 들어 c, C, 0xc, 0xC, 0Xc 및 0XC는 모두 10진수 12로 해석됩니다. 0-9 이외의 모든 문자, A-F, a-f, x 및 X는 숫자 변환을 종료합니다. 따라서 `"124n5"` 시퀀스는 [basic_ios::fail](../standard-library/basic-ios-class.md#fail) 비트가 설정된 숫자 124로 변환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [입력 스트림](../standard-library/input-streams.md)


