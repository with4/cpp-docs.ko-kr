---
title: "BSCMAKE 명령줄 | Microsoft Docs"
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
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c00a3842db37cc5027809f717ac47bd471dd073f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-command-line"></a>BSCMAKE 명령줄
BSCMAKE를 실행 하려면 다음 명령줄 구문을 사용 합니다.  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 옵션에만 나타날 수 있습니다는 `options` 명령줄에서 필드입니다.  
  
 *sbrfiles* 필드 컴파일러 또는 어셈블러에 의해 생성 된 하나 이상의.sbr 파일을 지정 합니다. .Sbr 파일의 이름을 공백이 나 탭으로 구분 합니다. 확장;를 지정 해야 합니다. 기본값은 없습니다. 파일 이름으로 경로 지정할 수 있습니다 및 운영 체제 와일드 카드 (* 및?).  
  
 증분 빌드를 하는 동안 원래 빌드의 일부로 포함 되지 않은 새.sbr 파일을 지정할 수 있습니다. 찾아보기 정보 파일을 유지 하기 위한 전체 기여를 하려는 경우 모든.sbr 파일 (잘린된 파일 포함)을 원래.bsc 파일을 만드는 데 사용 된을 지정 해야 합니다. .Sbr 파일을 생략 하는 경우 찾아보기 정보 파일에 대 한 구성 정보를 해당 파일의 제거 됩니다.  
  
 전체 빌드에 대 한 잘린된.sbr 파일을 지정 하지 마십시오. 전체 빌드 모든 지정 된.sbr 파일 정보를 필요로 합니다. 전체 빌드를 수행 하기 전에 프로젝트를 컴파일하고 비어 있는 각 파일에 대 한 새.sbr 파일을 만듭니다.  
  
 다음 명령은 MAIN.bsc 세.sbr 파일에서 호출 하는 파일을 작성 하는 BSCMAKE를 실행 합니다.  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 관련된 정보를 참조 하십시오. [BSCMAKE 명령 파일](../../build/reference/bscmake-command-file-response-file.md) 및 [BSCMAKE 옵션](../../build/reference/bscmake-options.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)