---
title: BSCMAKE 오류 BK1503 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1503
dev_langs:
- C++
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06d4a05a8f2d04c3f8a991d4444b35295408a7b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE 오류 BK1503
'filename' 파일에 쓸 수 없습니다 [: 이유]  
  
 BSCMAKE는 하나의 브라우저 데이터베이스로 컴파일하는 동안 생성 된.sbr 파일을 결합 합니다. 이 오류는 결과 브라우저 데이터베이스 64MB를 초과 하거나 입력 파일 (.sbr) 수가 4092 초과 하는 경우에 발생 합니다.  
  
 4092 개 이상의.sbr 파일에서 문제가 발생 하는 경우 입력된 파일의 수를 줄여야 합니다. Visual Studio 내에서 이렇게 하 여 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) 전체 프로젝트에 다음 파일 단위로 다시 확인 합니다.  
  
 64MB 보다 큰.bsc 파일에서 문제가 발생 하는 경우 입력으로.sbr 파일 수를 줄이면 결과.bsc 파일 크기를 감소 합니다. 또한 찾아보기 정보의 양은 /Em (매크로 확장 기호 제외), /El (지역 변수 제외) 및 /Es (시스템 파일 제외) 줄일 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [BSCMAKE 옵션](../../build/reference/bscmake-options.md)