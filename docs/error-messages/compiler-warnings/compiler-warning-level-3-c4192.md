---
title: "컴파일러 경고 (수준 3) C4192 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4192
dev_langs: C++
helpviewer_keywords: C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 022c0e0aac8d231963ddf6d5d3715d55f726a8b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4192"></a>컴파일러 경고 (수준 3) C4192
'name' 형식 라이브러리 'library'를 가져오는 동안 자동으로 제외 합니다.  
  
 A `#import` 라이브러리의 항목에 포함 되어 *이름*, 즉 Win32 시스템 헤더에도 정의 합니다. 형식 라이브러리의 제한 때문에 이름이 같은 **IUnknown** 또는 GUID는 종종에 정의 된 형식 라이브러리 시스템 헤더에서 정의 복제 합니다. `#import`에서는 이러한 항목을 검색 하 고.tlh 및.tli 헤더 파일에 통합 하 거부 합니다.  
  
 사용 하 여이 동작을 재정의 하려면 `#import` 특성 [no_auto_exclude](../../preprocessor/no-auto-exclude.md) 및 [include ()](../../preprocessor/include-parens.md)합니다.