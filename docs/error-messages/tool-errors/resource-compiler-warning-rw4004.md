---
title: "리소스 컴파일러 경고 RW4004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0249f7d01ee344f0fa17bdc39e58e9fce26c9b25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rw4004"></a>리소스 컴파일러 경고 RW4004
ASCII 문자가 가상 키 코드와 일치하지 않습니다.  
  
 VIRTKEY 형식 액셀러레이터의 가상 키 코드에 문자열 리터럴을 사용했습니다.  
  
 이 경고가 표시되어도 계속 진행할 수 있지만 생성된 액셀러레이터 키가 지정한 문자열과 일치하지 않을 수 있습니다. (VIRTKEY가 ASCII 액셀러레이터와 다른 키 코드를 사용합니다.)  
  
 문자열 리터럴이 구문상 유효한 상태인 있습니다만 확인할 수를 사용 하 여 원하는 액셀러레이터를 얻을 수는 **VK_\* #define** WINDOWS.h의 값입니다.