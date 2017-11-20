---
title: "STL/CLR 컨테이너 요소에 대 한 요구 사항 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f12bc8c3a6e2ecaa544ab5bbe875cc2ae358ef3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR 컨테이너 요소에 대한 요구 사항
STL/CLR 컨테이너에 삽입 된 모든 참조 형식에는 최소한 다음과 같은 요소가 있어야 합니다.  
  
-   공용 복사 생성자입니다.  
  
-   공용 대입 연산자입니다.  
  
-   Public 소멸자입니다.  
  
 또한 연관 컨테이너와 같은 [설정](../dotnet/set-stl-clr.md) 및 [지도](../dotnet/map-stl-clr.md) 되는 공용 비교 연산자를 정의 해야 `operator<` 기본적으로 합니다. 컨테이너의 일부 작업은 공용 기본 생성자와는 공용 연산자를 정의할 수에 필요할 수 있습니다.  
  
 참조 형식, 값 형식 및 핸들을 참조 하려면 같은 연관 컨테이너에 삽입 된 형식이 있어야 비교 연산자와 같은 `operator<` 정의 합니다. 공용 복사 생성자, 공용 할당 연산자 및 public 소멸자에 대 한 요구 사항을 참조 형식에는 값 형식 또는 핸들에 대 한 존재 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)