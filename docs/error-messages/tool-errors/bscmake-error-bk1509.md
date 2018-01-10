---
title: "BSCMAKE 오류 BK1509 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1509
dev_langs: C++
helpviewer_keywords: BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4d5fe0a83c5fbc3c4793699975d2045df5fbd8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1509"></a>BSCMAKE 오류 BK1509
힙 공간이 부족 합니다.  
  
 BSCMAKE 가상 메모리를 포함 하 여 메모리 부족 오류가 발생 했습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  디스크 공간을 확보 합니다.  
  
2.  스왑 파일의 크기를 늘립니다.  
  
3.  Windows 스왑 파일의 크기를 늘립니다.  
  
4.  BSCMAKE /Ei를 사용 하 여 필요한 메모리를 줄이거나 /Es 일부를 제거 하려면 입력 파일이 나 /Em으로 매크로 본문을 제거 합니다.