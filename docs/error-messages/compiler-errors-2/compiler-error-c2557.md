---
title: 컴파일러 오류 C2557 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2557
dev_langs:
- C++
helpviewer_keywords:
- C2557
ms.assetid: 48a33d82-aa16-4658-b346-2311fcb39864
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5402cb98d2cf315861ccb27aad3233b3bd370f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227410"
---
# <a name="compiler-error-c2557"></a>컴파일러 오류 C2557
'identifier': 전용 및 보호된 멤버는 생성자 없이 초기화할 수 없습니다.  
  
 멤버와 friend만 private 또는 protected 멤버에 값을 할당할 수 있습니다. public이 아닌 멤버는 클래스 생성자에서 초기화해야 합니다.