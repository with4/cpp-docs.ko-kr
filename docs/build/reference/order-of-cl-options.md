---
title: "CL 옵션 순서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords: cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fdcc4b315f2e223e59e88e2f5876965d106a49c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="order-of-cl-options"></a>CL 옵션 순서
옵션은 CL 명령줄의 마지막 발생 해야 하는 /link 옵션을 제외 하 고에서 아무 곳 이나 나타날 수 있습니다. 컴파일러에 지정 된 옵션으로 시작 된 [CL 환경 변수](../../build/reference/cl-environment-variables.md) 다음 왼쪽에서 오른쪽으로 명령줄을 읽습니다-을 발견 하면 순서로 명령 파일을 처리 합니다. 각 옵션은 명령줄에 모든 파일에 적용 됩니다. CL에서 충돌 하는 옵션을 가장 오른쪽 옵션이 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)