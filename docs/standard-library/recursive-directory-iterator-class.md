---
title: "recursive_directory_iterator 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
dev_langs:
- C++
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c432cde8a4c565e6195658ab27ce5f2cb1838f6a
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator 클래스
재귀적으로 하위 디렉터리로 상속될 수 있는 디렉터리의 파일 이름을 통해 시퀀스되는 입력 반복기에 대해 설명합니다. 반복기 X에 대해 식 *X는 파일 이름과 상태에 대해 알려진 모든 항목을 래핑하는 directory_entry 클래스의 개체로 계산됩니다.  
  
 자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
class recursive_directory_iterator;  
```  
  
## <a name="remarks"></a>설명  
 템플릿 클래스에는 다음 항목이 저장됩니다.  
  
1.  stack<pair\<directory_iterator, path>> 형식의 개체 - 여기서는 표시를 위해 mystack이라고 하며 순서를 지정할 디렉터리의 중첩을 나타냅니다.  
  
2.  directory_entry 형식의 개체 - 여기서는 myentry라고 하며 디렉터리 시퀀스에 있는 현재 파일 이름을 나타냅니다.  
  
3.  bool 형식의 개체 - 여기서는 no_push라고 하며 하위 디렉터리로 재귀적 상속이 사용되지 않는지 여부를 기록합니다.  
  
4.  directory_options 형식의 개체 - 여기서는 myoptions라고 하며 생성 시 설정된 옵션을 기록합니다.  
  
 recursive_directory_entry 형식의 기본 생성된 개체는 mystack.top().first에 시퀀스의 끝 반복기가 있으며 시퀀스의 끝 반복기를 나타냅니다. 예를 들어 def(디렉터리), def/ghi 및 jkl 항목과 함께 abc 디렉터리를 지정할 경우 코드는 다음과 같습니다.  
  
```  
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)  
    visit(next->path());
```  
  
 `path("abc/def/ghi") and path("abc/jkl").`인수를 사용하여 방문을 호출합니다. 다음과 같은 두 가지 방법으로 디렉터리 하위 트리를 통한 시퀀싱을 한정할 수 있습니다.  
  
1.  symlink 디렉터리는 값이 directory_options::follow_directory_symlink인 directory_options 인수를 사용하여 recursive_directory_iterator를 생성하는 경우에만 검색됩니다.  
  
2.  disable_recursion_pending을 호출하면 증분 중 나타나는 후속 디렉터리가 재귀적으로 검색되지 않습니다.  
  
## <a name="recursivedirectoryiteratordepth"></a>recursive_directory_iterator::depth  
  
```  
int depth() const;
```  
  
 mystack.size() - 1을 반환하므로 pval 깊이가 0입니다.  
  
## <a name="recursivedirectoryiteratordisablerecursionpending"></a>recursive_directory_iterator::disable_recursion_pending  
  
```  
void disable_recursion_pending();
```  
  
 멤버 함수가 no_push에 true를 저장합니다.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator!=  
  
```  
bool operator!=(const recursive_directory_iterator& right) const;
```  
  
 멤버 연산자는 !(*this == right)를 반환합니다.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator=  
  
```  
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;  
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;  
```  
  
 기본 멤버 대입 연산자가 예상대로 작동합니다.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator==  
  
```  
bool operator==(const recursive_directory_iterator& right) const;
```  
  
 멤버 연산자는 *this와 right가 둘 다 시퀀스의 끝 반복기이거나 둘 다 시퀀스의 끝 반복기가 아닌 경우에만 true를 반환합니다.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator*  
  
```  
const directory_entry& operator*() const;
```  
  
 멤버 연산자는 myentry를 반환합니다.  
  
## <a name="recursivedirectoryiteratoroperator-"></a>recursive_directory_iterator::operator->  
  
```  
const directory_entry * operator->() const;
```  
  
 &**this를 반환합니다.  
  
## <a name="recursivedirectoryiteratoroperator"></a>recursive_directory_iterator::operator++  
  
```  
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```  
  
 첫 번째 멤버 함수는 increment()를 호출한 다음 *this를 반환합니다. 두 번째 멤버 함수는 개체의 복사본을 만들고 increment()를 호출한 다음 복사본을 반환합니다.  
  
## <a name="recursivedirectoryiteratoroptions"></a>recursive_directory_iterator::options  
  
```  
directory_options options() const;
```  
  
 myoptions를 반환합니다.  
  
## <a name="recursivedirectoryiteratorpop"></a>recursive_directory_iterator::pop  
  
```  
void pop();
```  
  
 depth() == 0인 경우 개체가 시퀀스의 끝 반복기가 됩니다. 그렇지 않은 경우 멤버 함수는 현재(최하위) 디렉터리 검색을 종료하고 다음으로 낮은 깊이에서 다시 시작합니다.  
  
## <a name="recursivedirectoryiteratorrecursionpending"></a>recursive_directory_iterator::recursion_pending  
  
```  
bool recursion_pending() const;
```  
  
 !no_push를 반환합니다.  
  
## <a name="recursivedirectoryiteratorrecursivedirectoryiterator"></a>recursive_directory_iterator::recursive_directory_iterator  
  
```  
recursive_directory_iterator() noexcept;  
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const path& pval,  
    directory_options opts);

recursive_directory_iterator(const path& pval,  
    directory_options opts,  
    error_code& ec) noexcept;  
recursive_directory_iterator(const recursive_directory_iterator&) = default;  
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;  
```  
  
 첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 및 세 번째 생성자는 no_push에 false를 저장하고 myoptions에 directory_options::none을 저장한 다음 pval을 디렉터리로 열어 읽으려고 합니다. 성공할 경우 mystack 및 myentry를 초기화하여 디렉터리가 아닌 첫 번째 파일 이름을 중첩된 시퀀스에 지정하고, 실패할 경우 시퀀스의 끝 반복기를 생성합니다.  
  
 네 번째 및 다섯 번째 생성자는 먼저 myoptions에 opts를 저장한다는 점을 제외하면 두 번째 및 세 번째와 동일하게 동작합니다. 기본 생성자는 예상대로 작동합니다.  
  
## <a name="recursivedirectoryiteratorincrement"></a>recursive_directory_iterator::increment  
  
```  
recursive_directory_iterator& increment(error_code& ec) noexcept;  
```  
  
 함수가 중첩된 시퀀스에서 다음 파일 이름으로 이동하려고 합니다. 성공하면 해당 파일 이름을 myentry에 저장하고, 실패하면 시퀀스의 끝 반복기를 생성합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<파일 시스템 >  
  
 **네임스페이스:** std::tr2::sys  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)

