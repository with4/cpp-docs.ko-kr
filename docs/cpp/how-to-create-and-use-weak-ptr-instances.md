---
title: '방법: weak_ptr 인스턴스 만들기 및 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e51e523540e14905bef17edd52205c4d2102afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-and-use-weakptr-instances"></a>방법: weak_ptr 인스턴스 만들기 및 사용
개체의 내부 개체를 액세스 하는 방법의 저장 해야 경우에 따라 한 `shared_ptr` 참조 개수가 증가 발생 하지 않고 있습니다. 일반적으로이 상황이 발생 간의 순환 참조가 있는 경우 `shared_ptr` 인스턴스.  
  
 가장 좋은 디자인 가능 하면 항상 포인터의 공유 소유권을 방지 하기 위해입니다. 그러나 소유권을 공유 해야 하는 경우 `shared_ptr` 인스턴스 사이의 순환 참조를 방지 합니다. 사용 하 여 순환 참조를 피할 수 없는 경우, 또는 적합도 몇 가지 이유로 `weak_ptr` 소유자 중 하나 이상을 다른에 대 한 약한 참조를 부여할 `shared_ptr`합니다. 사용 하 여 한 `weak_ptr`를 만들 수 있습니다는 `shared_ptr` 기본 메모리 리소스가 여전히 유효한 경우에 관련 된 인스턴스의 기존 집합을 조인 하 합니다. A `weak_ptr` 참조 횟수가 0을 막을 수 없습니다 것 이므로 및 자체 참조 횟수에 참여 하지 않습니다. 사용할 수 있습니다는 `weak_ptr` 의 새 복사본을 확보는 `shared_ptr` 초기화 되었습니다. 메모리가 이미 삭제 된 경우는 **bad_weak_ptr** 예외가 throw 됩니다. 새 공유 포인터 참조 횟수를 증가 및가 메모리 유효 하도록 보장 하는 메모리가 여전히 유효한 경우으로 `shared_ptr` 변수 범위에 보관 됩니다.  
  
## <a name="example"></a>예  
 다음 코드 예제는 경우를 보여 줍니다. 여기서 `weak_ptr` 순환 종속성이 있는 개체의 적절 한 삭제를 확인 하는 데 사용 됩니다. 이 예제를 확인 하는 동안 대체 솔루션으로 간주 된 후에 만들어져 있다고 가정 합니다. `Controller` 개체 컴퓨터 프로세스의 일부 측면을 나타내고 독립적으로 작동 하기. 각 컨트롤러는 언제 든 지 다른 컨트롤러의 상태를 쿼리할 수 있어야 하 고 개인 포함 각각 `vector<weak_ptr<Controller>>` 이 목적을 위해 합니다. 각 벡터 순환 참조가 있으므로 `weak_ptr` 인스턴스가 대신 사용 됩니다 `shared_ptr`합니다.  
  
 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  
  
```Output  
Creating Controller0Creating Controller1Creating Controller2Creating Controller3Creating Controller4push_back to v[0]: 1push_back to v[0]: 2push_back to v[0]: 3push_back to v[0]: 4push_back to v[1]: 0push_back to v[1]: 2push_back to v[1]: 3push_back to v[1]: 4push_back to v[2]: 0push_back to v[2]: 1push_back to v[2]: 3push_back to v[2]: 4push_back to v[3]: 0push_back to v[3]: 1push_back to v[3]: 2push_back to v[3]: 4push_back to v[4]: 0push_back to v[4]: 1push_back to v[4]: 2push_back to v[4]: 3use_count = 1Status of 1 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 3 = OnDestroying Controller0Destroying Controller1Destroying Controller2Destroying Controller3Destroying Controller4Press any key  
```  
  
 시험 벡터 수정 `others` 되도록는 `vector<shared_ptr<Controller>>`, 출력 없는 소멸자를 호출 하는 확인 때 `TestRun` 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스마트 포인터](../cpp/smart-pointers-modern-cpp.md)