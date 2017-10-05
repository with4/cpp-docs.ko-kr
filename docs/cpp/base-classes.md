---
title: "기본 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inheritance, multiple
- base classes, virtual
- derived classes, multiple bases
- multiple inheritance, base classes
- virtual base classes
- base classes
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6b08321ffb027901683a4f85960579625ce98cc2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="base-classes"></a>기본 클래스
상속 프로세스는 기본 클래스의 멤버와 파생 클래스에 의해 추가된 모든 새 멤버로 구성된 새로운 파생 클래스를 만듭니다. 다중 상속에서는 동일한 기본 클래스가 둘 이상의 파생 클래스에 속하는 상속 그래프를 생성할 수 있습니다. 다음 그림에서는 이러한 그래프를 보여 줍니다.  
  
 ![기본 클래스의 여러 인스턴스](../cpp/media/vc38xn1.gif "vc38XN1")  
단일 기본 클래스의 여러 인스턴스  
  
 이 그림에는 `CollectibleString` 및 `CollectibleSortable`의 구성 요소가 설명되어 있습니다. 그러나 기본 클래스인 `Collectible`은 `CollectibleSortableString` 경로 및 `CollectibleString` 경로를 통해 `CollectibleSortable`에 있습니다. 이 중복성을 없애기 위해 상속 시 이러한 클래스를 가상 기본 클래스로 선언할 수 있습니다.  
  

