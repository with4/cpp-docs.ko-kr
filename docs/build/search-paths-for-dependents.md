---
title: "종속 항목에 대 한 경로 검색 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6093db4ac8e0c88dfe6e4b5a5463e5ee8d24349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="search-paths-for-dependents"></a>종속 파일의 경로 검색
각 종속 다음과 같이 지정 하는 선택적 검색 경로, 파일에:  
  
## <a name="syntax"></a>구문  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>설명  
 NMAKE 종속 먼저 현재 디렉터리에서에서 찾은 다음 지정한 순서에 따라 디렉터리에서 찾습니다. 매크로 일부 또는 전체 검색 경로를 지정할 수 있습니다. 디렉터리 이름을 중괄호 ({})로 묶습니다. 여러 디렉터리를 세미콜론 (;)으로 구분 합니다. 공백 또는 탭 없음 허용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [종속 파일](../build/dependents.md)