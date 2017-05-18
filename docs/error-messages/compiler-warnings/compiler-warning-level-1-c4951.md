---
title: "컴파일러 경고 (수준 1) C4951 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: 8
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
ms.openlocfilehash: da1b8904a6daf8e356cf65bb80f0fd36f467a35f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4951"></a>컴파일러 경고(수준 1) C4951
프로필 데이터가 수집된 이후 'function'이 편집되었습니다. 함수 프로필 데이터가 사용되지 않습니다.  
  
 함수에 대 한 입력된 모듈에서 편집 되어 [/ltcg: pgupdate](../../build/reference/ltcg-link-time-code-generation.md)하지 프로필 데이터는 사용할 수 있도록 합니다. **/LTCG:PGINSTRUMENT** 후에 입력 모듈이 다시 컴파일되었으며,***/LTCG:PGINSTRUMENT***작업 시 모듈에 있던 것과 다른 제어 흐름을 가진 함수( **function** )가 있습니다.  
  
 이 경고는 정보 제공용입니다. 이 경고를 해결하려면 **/LTCG:PGINSTRUMENT**를 실행하고 모든 테스트 실행을 다시 실행한 다음 **/LTCG:PGOPTIMIZE**를 실행합니다.  
  
 **/LTCG:PGOPTIMIZE** 를 사용한 경우 이 경고는 오류로 대체됩니다.
