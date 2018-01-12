---
title: "링커 도구 경고 LNK4102 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4102
dev_langs: C++
helpviewer_keywords: LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80efad60da9f6742110811a5cf4c12f07c7def67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4102"></a>링커 도구 경고 LNK4102
내보내기 삭제 중인 소멸자 'name'; 이미지가 올바르게 실행 되지 않을 수 있습니다.  
  
 프로그램 삭제 중인 소멸자를 내보내려고 했습니다. 프로세스에서 소유 하지 않은 메모리를 비울 수 되도록 DLL 경계를 넘어 삭제가 발생할 수 있습니다. .Def 파일에 지정 된 기호 되지 나열 되어 있는지 확인 기호 인수로 표시 되지 않는 **가져오기/** 또는 **/내보내기** 링커 명령줄에서 옵션입니다.  
  
 C 런타임 라이브러리를 다시 작성 하는 경우이 메시지를 무시할 수 있습니다.