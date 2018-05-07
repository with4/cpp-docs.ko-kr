---
title: 명령줄 경고 D9026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2d99573ee46c51178cc2fe995fa0f526b800f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9026"></a>명령줄 경고 D9026
옵션이 전체 명령줄에 적용  
  
 파일 이름이 지정 된 후 명령에는 옵션이 지정 되었습니다. 옵션은 선행 하는 파일에 적용 되었습니다.  
  
 예를 들어 명령에서  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 파일 VERDI.c 기본값인 /G4 대신에 /G5 옵션을 사용 하 여 컴파일됩니다.  
  
 이 동작은 적용 VERDI.c에 파일 이름 앞에 지정 된 옵션은 사용 하 여 컴파일 중인 / G4 및 PUCCINI.c 대신에 /G5를 사용 하 여 컴파일 중인 일부 이전 버전의 다릅니다.