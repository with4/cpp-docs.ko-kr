---
title: "링커 도구 오류 LNK1106 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 793d788462a3a449c654c30ec874399a3bb85728
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1106"></a>링커 도구 오류 LNK1106
잘못 된 파일 또는 전체 디스크: 위치를 찾을 수 없습니다  
  
 도구를 읽거나 수 없습니다에 쓸 `location` 메모리 매핑된 파일에 있습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  디스크가 꽉 찼습니다.  
  
     공간을 해제 하 고 다시 연결 합니다.  
  
2.  네트워크를 통해 연결 하려고 합니다.  
  
     일부 네트워크 링커에 의해 사용 되는 메모리 매핑된 파일을 완벽 하 게 지원 하지 않습니다. 로컬 디스크에 연결을 시도 합니다.  
  
3.  디스크에 불량 블록입니다.  
  
     운영 체제 및 하드웨어 디스크는는 이러한 오류가 감지, 하지만 디스크 검사 프로그램을 실행 하는 것이 좋습니다.  
  
4.  힙 공간이 부족 합니다.  
  
     참조 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 자세한 정보에 대 한 합니다.