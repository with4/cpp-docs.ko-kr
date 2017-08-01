---
title: "구조체 멤버 채우기 및 맞춤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 4c1632e0b987d0622bce6707d31ff1f5a4cb8498
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="padding-and-alignment-of-structure-members"></a>구조체 멤버 채우기 및 맞춤
**ANSI 3.5.2.1** 구조체 멤버의 채우기 및 맞춤과 비트 필드가 저장소 단위 경계에 걸쳐 있을 수 있는지 여부  
  
 구조체 멤버는 선언된 순서에 따라 순차적으로 저장됩니다. 즉, 첫 멤버가 가장 낮은 메모리 주소를 갖고 마지막 멤버가 가장 높은 주소를 갖습니다.  
  
 모든 데이터 개체에는 맞춤 요구 사항이 있습니다. 구조체, 공용 구조체 및 배열을 제외한 모든 데이터에 대한 맞춤 요구 사항은 개체의 크기 또는 현재 압축 크기(/Zp 또는 `pack` pragma 중에서 작은 것으로 지정됨)입니다. 구조체, 공용 구조체 및 배열에 대한 맞춤 요구 사항은 해당 멤버의 최대 맞춤 요구 사항입니다. 다음과 같이 되도록 모든 개체에 오프셋이 할당됩니다.  
  
 *offset*  `%` *alignment-requirement* `==` 0  
  
 정수 계열 형식의 크기가 같으며 다음 비트 필드가 비트 필드의 일반 할당 요구 사항에 따라 적용되는 경계를 벗어나지 않고 현재 할당 단위에 맞는 경우 인접 비트 필드는 동일한 1, 2 또는 4바이트 할당 단위로 압축됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 공용 구조체, 열거형 및 비트 필드](../c-language/structures-unions-enumerations-and-bit-fields.md)
