---
title: "컴파일러 오류 C3744 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: f6cd256454b51a103d9c4249b050c8c05781bc78
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3744"></a>컴파일러 오류 C3744
관리되는 이벤트의 경우 __unhook를 사용하려면 인수가 적어도 3개는 있어야 합니다.  
  
 [__unhook](../../cpp/unhook.md) 함수는 c + +에 대 한 관리 되는 확장에 대 한 컴파일된 프로그램에서 사용 하는 경우 세 개의 매개 변수를 사용 해야 합니다.  
  
 `__hook`및 `__unhook` /clr 프로그래밍와 호환 되지 않습니다. 대신 + = 및-= 연산자를 사용 합니다.  
  
 C3744는 사용 되지 않는 컴파일러 옵션을 사용 하 여 연결할 수만 **/clr:oldSyntax**합니다.  

