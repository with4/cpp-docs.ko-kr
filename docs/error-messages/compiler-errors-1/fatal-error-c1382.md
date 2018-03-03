---
title: "심각한 오류 C1382 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 923cc957dd136147a6c749f5ebf9508ca7e2052d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1382"></a>심각한 오류 C1382
'file' PCH 파일이 'o b j'가 생성 된 후 다시 빌드 되었습니다. 이 개체를 다시 빌드하세요.  
  
 사용 하는 경우 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), 컴파일러에서 가리키는 CIL.obj 보다 최신일.pch 파일을 발견 했습니다. CIL.obj 파일에 정보가 최신이 아닙니다. 개체를 다시 작성 합니다.  
  
 로 컴파일할 경우에 C1382 발생할 수 있습니다 **/Yc**, 하지만 컴파일러에 여러 개의 소스 코드 파일을도 전달 합니다.  를 해결 하려면 사용 하지 마십시오 **/Yc** 컴파일러에 여러 개의 소스 코드 파일을 전달 하는 경우.  자세한 내용은 참조 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)합니다.