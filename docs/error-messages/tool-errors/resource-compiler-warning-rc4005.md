---
title: "리소스 컴파일러 오류 RC4005 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC4005
dev_langs: C++
helpviewer_keywords: RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f27de973f0ff18493c182bdf1feb3f2812f39af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4005"></a>리소스 컴파일러 오류 RC4005
'identifier': 매크로 재정의  
  
 식별자가 두 번 정의 되었습니다. 컴파일러는 두 번째 매크로 정의 사용 합니다.  
  
 명령줄에서를 사용 하 여 코드에서 매크로 정의 하 여이 경고를 발생할 수 있습니다는 `#define` 지시문입니다. 또한 것 추가 포함 파일에서 가져온 매크로 발생할 수 있습니다.  
  
 이 경고를 제거 하려면 정의 중 하나를 제거 하거나 사용는 `#undef` 두 번째 정의 하기 전에 지시문입니다.