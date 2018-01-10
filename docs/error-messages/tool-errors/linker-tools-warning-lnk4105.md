---
title: "링커 도구 경고 LNK4105 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4105
dev_langs: C++
helpviewer_keywords: LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 913a6da056908def8df5aab1c2425ef9a187c1e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4105"></a>링커 도구 경고 LNK4105
'option'; 옵션에 지정 된 인수 없음 옵션을 무시합니다.  
  
 이 경고에만 발생 때는 [/LIBPATH](../../build/reference/libpath-additional-libpath.md) 옵션을 설정 합니다. 디렉터리를 지정 하지이 옵션을 링커 옵션 무시 및이 경고 메시지를 생성 합니다.  
  
 기존 환경 라이브러리 설정을 다시 정의 하도록 필요 하지 않은 경우 링커 명령줄에서 /LIBPATH 옵션을 제거 합니다. 라이브러리에 대 한 대체 검색 경로 사용 하려는 경우 /LIBPATH 옵션 다음에 대체 경로 지정 합니다.  
  
## <a name="example"></a>예  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 구문을 사용 하면 링커가에 필요한 라이브러리를 검색할 `c:\filepath\lib` 기본 위치를 검색 하기 전에.