---
title: "컴파일러 경고 (수준 1) C4819 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b515a3f5e840bbc93f37420866023ee778b404ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4819"></a>컴파일러 경고(수준 1) C4819
현재 코드 페이지(번호)에서 표시할 수 없는 문자가 파일에 들어 있습니다. 데이터가 손실되지 않게 하려면 해당 파일을 유니코드 형식으로 저장하세요.  
  
 파일의 모든 문자를 표시할 수는 없는 코드 페이지를 사용하여 시스템에서 ANSI 소스 파일을 컴파일하면 C4819가 발생합니다.  
  
 C4819를 해결하려면 유니코드 형식으로 파일을 저장합니다. Visual Studio에서 선택 **파일**, **고급 저장 옵션**합니다. 에 **고급 저장 옵션** 대화 상자에서 파일의 모든 문자를 나타낼 수 있는 인코딩을 선택-예를 들어 u t F-8-선택한 후 **확인**합니다.