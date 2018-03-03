---
title: "BSCMAKE 오류 BK1503 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK1503
dev_langs:
- C++
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86f2b6d282857409cdb1e1d49e04775e9886cde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE 오류 BK1503
'filename' 파일에 쓸 수 없습니다 [: 이유]  
  
 BSCMAKE는 하나의 브라우저 데이터베이스로 컴파일하는 동안 생성 된.sbr 파일을 결합 합니다. 이 오류는 결과 브라우저 데이터베이스 64MB를 초과 하거나 입력 파일 (.sbr) 수가 4092 초과 하는 경우에 발생 합니다.  
  
 4092 개 이상의.sbr 파일에서 문제가 발생 하는 경우 입력된 파일의 수를 줄여야 합니다. Visual Studio 내에서 이렇게 하 여 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) 전체 프로젝트에 다음 파일 단위로 다시 확인 합니다.  
  
 64MB 보다 큰.bsc 파일에서 문제가 발생 하는 경우 입력으로.sbr 파일 수를 줄이면 결과.bsc 파일 크기를 감소 합니다. 또한 찾아보기 정보의 양은 /Em (매크로 확장 기호 제외), /El (지역 변수 제외) 및 /Es (시스템 파일 제외) 줄일 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [BSCMAKE 옵션](../../build/reference/bscmake-options.md)