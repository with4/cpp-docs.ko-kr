---
title: "라이브러리의 구조 | Microsoft Docs"
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
- libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1630636b0de552712f67bc43b5182f991b10ef0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="structure-of-a-library"></a>라이브러리 구조
COFF 개체를 포함 하는 라이브러리입니다. 라이브러리의 개체에에서는 함수 및 프로그램의 다른 개체에서 외부에서 참조 될 수 있는 데이터를 포함 합니다. 라이브러리의 개체 라이브러리 멤버 라고도 합니다.  
  
 /LINKERMEMBER 옵션과 함께 DUMPBIN 도구를 실행 하 여 라이브러리의 내용에 대 한 추가 정보를 얻을 수 있습니다. 이 옵션에 대 한 자세한 내용은 참조 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LIB 개요](../../build/reference/overview-of-lib.md)