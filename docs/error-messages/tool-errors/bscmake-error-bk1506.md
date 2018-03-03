---
title: "BSCMAKE 오류 BK1506 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f553646689fd1e703e10f100bca6d989c8f767d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE 오류 BK1506
'filename' 파일을 열 수 없습니다 [: 이유]  
  
 BSCMAKE는 파일을 열 수 없습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  다른 프로세스에 의해 잠겨 파일입니다. 경우 `reason` 에 따르면 **사용 권한이 거부**, 브라우저가 파일을 사용 중일 수 있습니다. 찾아보기 창을 닫고 다시 빌드하십시오.  
  
2.  디스크가 꽉 찼습니다.  
  
3.  하드웨어 오류가 발생 합니다.  
  
4.  지정된 된 출력 파일 이름이 같은 기존 하위 디렉터리에 있습니다.