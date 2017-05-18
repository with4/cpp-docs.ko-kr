---
title: "심각한 오류 C1352 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1352
dev_langs:
- C++
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 66584dc786a3340deeaf1176362bf64dafacd3b8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1352"></a>심각한 오류 C1352
'file' 모듈의 'function' 함수에 잘못되었거나 손상된 MSIL이 있습니다.  
  
 .netmodule이 컴파일러에 전달되었지만 컴파일러가 파일에서 손상된 부분을 발견했습니다.  .netmodule을 생성한 사람에게 조사하도록 요청하세요.  
  
 컴파일러는 .netmodule 파일에서 모든 유형의 손상을 확인하지 않습니다.  그러나 함수의 모든 제어 경로에 return 문이 포함되어 있는지 확인합니다.  
  
 자세한 내용은 참조 [링커 입력 파일로.netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)합니다.
