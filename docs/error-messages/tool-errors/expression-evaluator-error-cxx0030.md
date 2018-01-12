---
title: "식 계산기 오류 CXX0030 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0030
dev_langs: C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb120103714c3711fb059fa736398458209b52a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0030"></a>식 계산기 오류 CXX0030
식을 계산할 수 없습니다.  
  
 작성 된 대로 디버거의 식 계산기는 식에 대 한 값을 얻을 수 있습니다. 프로그램의 주소 공간 밖에 있는 메모리에 식이 참조 때문일 (한 가지 예는 null 포인터 역참조). Windows는 프로그램의 주소 공간 범위 밖에 있는 메모리에 대 한 액세스를 허용 하지 않습니다.  
  
 평가 순서를 제어 하려면 괄호를 사용 하 여 식을 다시 작성 해야 합니다.  
  
 이 오류는 can0030과 동일 합니다.