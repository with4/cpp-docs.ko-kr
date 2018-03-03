---
title: "일반 c + + 클래스 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.generic
dev_langs:
- C++
helpviewer_keywords:
- Generic C++ Class Wizard [C++]
ms.assetid: aa95be9e-fc1b-45db-a11d-0d32c4929077
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82d706c30c729f490f6bfdec3344d5dab537a689
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="generic-c-class-wizard"></a>일반 C++ 클래스 마법사
일반 c + + 클래스를 프로젝트에 추가 합니다. 클래스는 ATL 또는 MFC 로부터 상속 되지 않습니다.  
  
 **클래스 이름**  
 새 클래스의 이름을 설정합니다.  
  
 **.h 파일**  
 새 클래스에 대 한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **클래스 이름**합니다. 헤더 파일의 선택한 위치에 저장 하거나 기존 파일에 클래스 선언을 추가 하려면 줄임표 단추를 클릭 (**...** ). 클릭할 때 기존 파일을 지정 하는 경우 **마침**, 마법사 클래스 선언 파일의 내용을 추가 해야 할지 여부를 지정 하 라는 메시지를 표시 합니다. 선언에 추가 하려면 클릭 **예**마법사로 돌아가서 및 다른 파일 이름을 지정 하 고, 클릭 하려면 **아니요**합니다.  
  
 **.cpp 파일**  
 새 클래스에 대 한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **클래스 이름**합니다. 구현 파일의 선택한 위치에 저장 하거나 기존 파일을 클래스 정의 추가 하려면 줄임표 단추를 클릭 (**...** ). 클릭할 때 기존 파일을 지정 하는 경우 **마침**, 마법사 클래스 정의 파일의 내용을 추가 해야 할지 여부를 지정 하 라는 메시지를 표시 합니다. 정의 추가 하려면 클릭 **예**마법사로 돌아가서 및 다른 파일 이름을 지정 하 고, 클릭 하려면 **아니요**합니다.  
  
 **기본 클래스**  
 새 클래스에 대 한 기본 클래스를 설정합니다.  
  
 **Access**  
 새 클래스에 대 한 기본 클래스 멤버에 액세스를 설정 합니다. 액세스 한정자는 다른 클래스는 클래스 멤버 함수에 포함 되는 액세스 수준을 지정 하는 키워드입니다. 액세스를 지정 하는 방법에 대 한 자세한 내용은 참조 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)합니다. 로 설정 하는 클래스 액세스 수준은 기본적으로 `public`합니다.  
  
-   `public`  
  
-   `protected`  
  
-   `private`  
  
-   **기본** (어떠한 액세스 한정자 생성 됩니다.)  
  
 **가상 소멸자**  
 클래스 소멸자는 가상이 있는지 여부를 지정 합니다. 가상 소멸자를 사용 하 여 사용 하는 파생 된 클래스의 인스턴스를 삭제할 때 올바른 소멸자가 호출 됩니다.  
  
 **인라인**  
 헤더 파일에서 클래스 생성자와 인라인 함수로 클래스 정의 생성합니다.  
  
 **관리 되는**  
 옵션을 선택 하면 관리 되는 클래스와 헤더 파일을 추가 합니다. 선택을 취소 하면 네이티브 클래스와 헤더 파일을 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [일반 C++ 클래스 추가](../ide/adding-a-generic-cpp-class.md)