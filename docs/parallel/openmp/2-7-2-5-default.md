---
title: "2.7.2.5 기본 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ee328be7f9f0c4876738f8179c26e700c57702c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="2725-default"></a>2.7.2.5 기본값
**기본** 절 변수 데이터 공유 특성에 영향을 줄 수 있습니다. 구문은 **기본** 절은 다음과 같습니다.  
  
```  
default(shared | none)  
```  
  
 지정 **default(shared)** 에 현재 표시 각 변수를 명시적으로 나열 하는 것과 같습니다는 **공유** 절은 아닌 경우 **threadprivate** 또는 **단점**`t`-정규화 합니다. 명시적으로 지정 하지 않을 경우 **기본** 절, 기본 동작은 동일 if **default(shared)** 지정 되었습니다.  
  
 지정 **밑** 하려면 다음 중 적어도 하나는 병렬 구문 어휘 범위에서 변수에 대 한 모든 참조에 대해 true 여야 합니다.  
  
-   변수 참조를 포함 하는 구문의 데이터 공유 특성 절에 명시적으로 나열 됩니다.  
  
-   변수는 병렬 구문 내에서 선언 됩니다.  
  
-   변수가 **threadprivate**합니다.  
  
-   변수가 한 **const**-형식을 한정 합니다.  
  
-   변수가 대 한 루프 제어 변수는 **에 대 한** 바로 뒤에 오는 루프는 **에 대 한** 또는 **에 대 한 병렬** 루프 내 표시 지시문 및 변수 참조 .  
  
 변수를 지정 하는 **firstprivate**, **lastprivate**, 또는 **감소** 괄호로 묶은 지시문의 절 하면 바깥쪽의 변수에 대 한 암시적 참조가 컨텍스트입니다. 이러한 암시적 참조 위에 나열 된 요구 사항이 적용 됩니다.  
  
 단일 **기본** 절에 지정할 수 있습니다는 **병렬** 지시문입니다.  
  
 변수의 기본 데이터 공유 특성을 사용 하 여 재정의할 수 있습니다는 **개인**, **firstprivate**, **lastprivate**, **감소**, 및 **공유** 다음 예제에서 보여주듯이 절:  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```