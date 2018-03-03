---
title: "명령줄 경고 D9026 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9127ad1887d476e5460798f806c2db1ff3144de3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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