---
title: "&lt;atomic&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<atomic>"
  - "atomic/std::atomic_int_least32_t"
  - "atomic/std::atomic_ullong"
  - "atomic/std::atomic_ptrdiff_t"
  - "atomic/std::atomic_char16_t"
  - "atomic/std::atomic_schar"
  - "atomic/std::atomic_ulong"
  - "atomic/std::atomic_uint_fast32_t"
  - "atomic/std::atomic_uint8_t"
  - "atomic/std::atomic_int32_t"
  - "atomic/std::atomic_uint_fast64_t"
  - "atomic/std::atomic_uint32_t"
  - "atomic/std::atomic_int16_t"
  - "atomic/std::atomic_uintmax_t"
  - "atomic/std::atomic_intmax_t"
  - "atomic/std::atomic_long"
  - "atomic/std::atomic_int"
  - "atomic/std::atomic_uint_least8_t"
  - "atomic/std::atomic_size_t"
  - "atomic/std::atomic_uint_fast16_t"
  - "atomic/std::atomic_wchar_t"
  - "atomic/std::atomic_int_fast64_t"
  - "atomic/std::atomic_uint_fast8_t"
  - "atomic/std::atomic_int_fast8_t"
  - "atomic/std::atomic_intptr_t"
  - "atomic/std::atomic_uint"
  - "atomic/std::atomic_uint16_t"
  - "atomic/std::atomic_char32_t"
  - "atomic/std::atomic_uint64_t"
  - "atomic/std::atomic_ushort"
  - "atomic/std::atomic_int_least16_t"
  - "atomic/std::atomic_char"
  - "atomic/std::atomic_uint_least32_t"
  - "atomic/std::atomic_uintptr_t"
  - "atomic/std::atomic_short"
  - "atomic/std::atomic_llong"
  - "atomic/std::atomic_uint_least16_t"
  - "atomic/std::atomic_int_fast16_t"
  - "atomic/std::atomic_int_least8_t"
  - "atomic/std::atomic_int_least64_t"
  - "atomic/std::atomic_int_fast32_t"
  - "atomic/std::atomic_uchar"
  - "atomic/std::atomic_int8_t"
  - "atomic/std::atomic_int64_t"
  - "atomic/std::atomic_uint_least64_t"
dev_langs: 
  - "C++"
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
caps.latest.revision: 22
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;atomic&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Defines classes and template classes to use to create types that support atomic operations.  
  
## 구문  
  
```cpp  
#include <atomic>  
```  
  
## 설명  
  
> [!NOTE]
>  In code that's compiled by using **\/clr** or **\/clr:pure**, this header is blocked.  
  
 An atomic operation has two key properties that help you use multiple threads to correctly manipulate an object without using mutex locks.  
  
-   Because an atomic operation is indivisible, a second atomic operation on the same object from a different thread can obtain the state of the object only before or after the first atomic operation.  
  
-   Based on its [memory\_order](../Topic/memory_order%20Enum.md) argument, an atomic operation establishes ordering requirements for the visibility of the effects of other atomic operations in the same thread.  Consequently, it inhibits compiler optimizations that violate the ordering requirements.  
  
 On some platforms, it might not be possible to efficiently implement atomic operations for some types without using `mutex` locks.  An atomic type is *lock\-free* if no atomic operations on that type use locks.  
  
 The class [atomic\_flag](../standard-library/atomic-flag-structure.md) provides a minimal atomic type that holds a `bool` flag.  Its operations are always lock\-free.  
  
 The template class `atomic<Ty>` stores an object of its argument type `Ty` and provides atomic access to that stored value.  You can instantiate it by using any type that can be copied by using [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) and tested for equality by using [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md).  In particular, you can use it with user\-defined types that meet these requirements and, in many cases, with floating\-point types.  
  
 The template also has a set of specializations for integral types and a partial specialization for pointers.  These specializations provide additional operations that are not available through the primary template.  
  
## Pointer Specializations  
 The `atomic<Ty *>` partial specializations apply to all pointer types.  They provide methods for pointer arithmetic.  
  
## Integral Specializations  
 The `atomic<integral>` specializations apply to all integral types.  They provide additional operations that are not available through the primary template.  
  
 Each `atomic<integral>` type has a corresponding macro that you can use in an `if directive` to determine at compile time whether operations on that type are lock\-free.  If the value of the macro is zero, operations on the type are not lock\-free.  If the value is 1, operations might be lock\-free, and a runtime check is required.  If the value is 2, operations are lock\-free.  You can use the function `atomic_is_lock_free` to determine at runtime whether operations on the type are lock\-free.  
  
 For each of the integral types, there is a corresponding named atomic type that manages an object of that integral type.  Each `atomic_integral` type has the same set of member functions as the corresponding instantiation of `atomic<Ty>` and can be passed to any of the non\-member atomic functions.  
  
|`atomic_integral` 형식|Integral Type|`atomic_is_lock_free` Macro|  
|--------------------------|-------------------|---------------------------------|  
|`atomic_char`|`char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_schar`|`signed char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_uchar`|`unsigned char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_char16_t`|`char16_t`|`ATOMIC_CHAR16_T_LOCK_FREE`|  
|`atomic_char32_t`|`char32_t`|`ATOMIC_CHAR32_T_LOCK_FREE`|  
|`atomic_wchar_t`|`wchar_t`|`ATOMIC_WCHAR_T_LOCK_FREE`|  
|`atomic_short`|`short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_ushort`|`unsigned short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_int`|`int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_uint`|`unsigned int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_long`|`long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_ulong`|`unsigned long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_llong`|`long long`|`ATOMIC_LLONG_LOCK_FREE`|  
|`atomic_ullong`|`unsigned long long`|`ATOMIC_LLONG_LOCK_FREE`|  
  
 Typedef names exist for specializations of the atomic template for some of the types that are defined in the header \<inttypes.h\>.  
  
|Atomic Type|Typedef Name|  
|-----------------|------------------|  
|`atomic_int8_t`|`atomic<int8_t>`|  
|`atomic_uint8_t`|`atomic<uint8_t>`|  
|`atomic_int16_t`|`atomic<int16_t>`|  
|`atomic_uint16_t`|`atomic<uint16_t>`|  
|`atomic_int32_t`|`atomic<int32_t>`|  
|`atomic_uint32_t`|`atomic<uint32_t>`|  
|`atomic_int64_t`|`atomic<int64_t>`|  
|`atomic_uint64_t`|`atomic<uint64_t>`|  
|`atomic_int_least8_t`|`atomic<int_least8_t>`|  
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|  
|`atomic_int_least16_t`|`atomic<int_least16_t>`|  
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|  
|`atomic_int_least32_t`|`atomic<int_least32_t>`|  
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|  
|`atomic_int_least64_t`|`atomic<int_least64_t>`|  
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|  
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|  
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|  
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|  
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|  
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|  
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|  
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|  
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|  
|`atomic_intptr_t`|`atomic<intptr_t>`|  
|`atomic_uintptr_t`|`atomic<uintptr_t>`|  
|`atomic_size_t`|`atomic<size_t>`|  
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|  
|`atomic_intmax_t`|`atomic<intmax_t>`|  
|`atomic_uintmax_t`|`atomic<uintmax_t>`|  
  
## Structs  
  
|Name|설명|  
|----------|--------|  
|[atomic 구조체](../standard-library/atomic-structure.md)|Describes an object that performs atomic operations on a stored value.|  
|[atomic\_flag 구조체](../standard-library/atomic-flag-structure.md)|설명 원자 단위로 설정하고 `bool` 플레그를 해제합니다.|  
  
## 열거형  
  
|Name|설명|  
|----------|--------|  
|[memory\_order Enum](../Topic/memory_order%20Enum.md)|메모리 위치에 동기화 연산에 대한 기호 이름을 제공합니다.  이러한 연산은 하나의 스레드의 할당이 다른 스레드에 표시 될 방법에 영향을 미칩니다.|  
  
## 함수  
 In the following list, the functions that do not end in `_explicit` have the semantics of the corresponding `_explicit`, except that they have the implicit [memory\_order](../Topic/memory_order%20Enum.md) arguments of `memory_order_seq_cst`.  
  
|Name|설명|  
|----------|--------|  
|[atomic\_compare\_exchange\_strong 함수](../Topic/atomic_compare_exchange_strong%20Function.md)|수행 된 *원자 비교 및 교환* 에서 작업합니다.|  
|[atomic\_compare\_exchange\_strong\_explicit 함수](../Topic/atomic_compare_exchange_strong_explicit%20Function.md)|수행 된 *원자 비교 및 교환* 에서 작업합니다.|  
|[atomic\_compare\_exchange\_weak 함수](../Topic/atomic_compare_exchange_weak%20Function.md)|이 *약한 원자 비교 및 교환* 작업을 수행합니다.|  
|[atomic\_compare\_exchange\_weak\_explicit 함수](../Topic/atomic_compare_exchange_weak_explicit%20Function.md)|이 *약한 원자 비교 및 교환* 작업을 수행합니다.|  
|[atomic\_exchange 함수](../Topic/atomic_exchange%20Function.md)|Replaces a stored value.|  
|[atomic\_exchange\_explicit 함수](../Topic/atomic_exchange_explicit%20Function.md)|Replaces a stored value.|  
|[atomic\_fetch\_add 함수](../Topic/atomic_fetch_add%20Function.md)|Adds a specified value to an existing stored value.|  
|[atomic\_fetch\_add\_explicit 함수](../Topic/atomic_fetch_add_explicit%20Function.md)|Adds a specified value to an existing stored value.|  
|[atomic\_fetch\_and 함수](../Topic/atomic_fetch_and%20Function.md)|Performs a bitwise `and` on a specified value and an existing stored value.|  
|[atomic\_fetch\_and\_explicit 함수](../Topic/atomic_fetch_and_explicit%20Function.md)|Performs a bitwise `and` on a specified value and an existing stored value.|  
|[atomic\_fetch\_or 함수](../Topic/atomic_fetch_or%20Function.md)|Performs a bitwise `or` on a specified value and an existing stored value.|  
|[atomic\_fetch\_or\_explicit 함수](../Topic/atomic_fetch_or_explicit%20Function.md)|Performs a bitwise `or` on a specified value and an existing stored value.|  
|[atomic\_fetch\_sub 함수](../Topic/atomic_fetch_sub%20Function.md)|Subtracts a specified value from an existing stored value.|  
|[atomic\_fetch\_sub\_explicit 함수](../Topic/atomic_fetch_sub_explicit%20Function.md)|Subtracts a specified value from an existing stored value.|  
|[atomic\_fetch\_xor 함수](../Topic/atomic_fetch_xor%20Function.md)|Performs a bitwise `exclusive or` on a specified value and an existing stored value.|  
|[atomic\_fetch\_xor\_explicit 함수](../Topic/atomic_fetch_xor_explicit%20Function.md)|Performs a bitwise `exclusive or` on a specified value and an existing stored value.|  
|[atomic\_flag\_clear 함수](../Topic/atomic_flag_clear%20Function.md)|Sets the flag in an `atomic_flag` object to `false`.|  
|[atomic\_flag\_clear\_explicit 함수](../Topic/atomic_flag_clear_explicit%20Function.md)|Sets the flag in an `atomic_flag` object to `false`.|  
|[atomic\_flag\_test\_and\_set 함수](../Topic/atomic_flag_test_and_set%20Function.md)|Sets the flag in an `atomic_flag` object to `true`.|  
|[atomic\_flag\_test\_and\_set\_explicit 함수](../Topic/atomic_flag_test_and_set_explicit%20Function.md)|Sets the flag in an `atomic_flag` object to `true`.|  
|[atomic\_init 함수](../Topic/atomic_init%20Function.md)|Sets the stored value in an `atomic` object.|  
|[atomic\_is\_lock\_free 함수](../Topic/atomic_is_lock_free%20Function.md)|Specifies whether atomic operations on a specified object are lock\-free.|  
|[atomic\_load 함수](../Topic/atomic_load%20Function.md)|Atomically retrieves a value.|  
|[atomic\_load\_explicit 함수](../Topic/atomic_load_explicit%20Function.md)|Atomically retrieves a value.|  
|[atomic\_signal\_fence 함수](../Topic/atomic_signal_fence%20Function.md)|Acts as a *fence* that establishes memory ordering requirements between fences in a calling thread that has signal handlers executed in the same thread.|  
|[atomic\_store 함수](../Topic/atomic_store%20Function.md)|Atomically stores a value.|  
|[atomic\_store\_explicit 함수](../Topic/atomic_store_explicit%20Function.md)|Atomically stores a value.|  
|[atomic\_thread\_fence 함수](../Topic/atomic_thread_fence%20Function.md)|Acts as a *fence* that establishes memory ordering requirements with respect to other fences.|  
|[kill\_dependency 함수](../Topic/kill_dependency%20Function.md)|Breaks a possible dependency chain.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)