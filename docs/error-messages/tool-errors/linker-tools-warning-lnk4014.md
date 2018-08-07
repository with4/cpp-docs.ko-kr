---
title: 링커 도구 경고 LNK4014 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4014
dev_langs:
- C++
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fb86efbdc70342861a87a233ab687f7564cb48b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300061"
---
# <a name="linker-tools-warning-lnk4014"></a>링커 도구 경고 LNK4014
멤버 개체 "objectname"를 찾을 수 없습니다.  
  
 LIB를 찾을 수 없습니다 `objectname` 라이브러리에 있습니다.  
  
 **제거/** 및 **추출/** 옵션을 삭제할지 아니면 파일에 복사 되는 멤버 개체의 전체 이름이 필요 합니다. 원래 개체 파일의 경로 포함 하는 전체 이름입니다. 라이브러리에 있는 구성원 개체의 전체 이름을 보려면 사용 DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) 또는 LIB [/list](../../build/reference/managing-a-library.md)합니다.