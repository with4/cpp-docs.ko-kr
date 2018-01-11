---
title: "링커 도구 경고 LNK4014 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4014
dev_langs: C++
helpviewer_keywords: LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e0e0e87fb9c8e6006c62e07b7bb9b6435a22dd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4014"></a>링커 도구 경고 LNK4014
멤버 개체 "objectname"를 찾을 수 없습니다.  
  
 LIB를 찾을 수 없습니다 `objectname` 라이브러리에 있습니다.  
  
 **제거/** 및 **추출/** 옵션을 삭제할지 아니면 파일에 복사 되는 멤버 개체의 전체 이름이 필요 합니다. 원래 개체 파일의 경로 포함 하는 전체 이름입니다. 라이브러리에 있는 구성원 개체의 전체 이름을 보려면 사용 DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) 또는 LIB [/list](../../build/reference/managing-a-library.md)합니다.