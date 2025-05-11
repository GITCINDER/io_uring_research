# Task 2: Dependency Injection
For this assigment, we want a little clarity regarding what kind of functions being imported and used on each source. Do note, we record all function actually being used by the source including function defined by itself if actually used inside the file. For the sake of completion, it's better if you straight disregard include list on the source. Instead, trace each function being used to the declared source.

Source | Libary | Function utilized | Time Used
-------|--------|--------------| ------------------
alloc_cache.h | /include/linux/kasan.h | kasan_mempool_unpoison_object | 1
| | arch/x86/include/asm/string_64.h| memset | 1
| | alloc_cache.h | io_alloc_cache_get | 1
| | alloc_cache.h | io_cache_alloc_new | 1
| | alloc_cache.h | io_alloc_cache_put | 1
| | linux/mm/slub.c | kfree | 1
io_uring.c | include/linux/syscalls.h	| SYSCALL_DEFINE2	| 1
io_uring.c	|include/linux/syscalls.h	|SYSCALL_DEFINE6	|1
io_uring.c	include/linux/err.h	IS_ERR	2
io_uring.c	include/linux/err.h	PTR_ERR	2
io_uring.c	include/linux/err.h	ERR_PTR	2
io_uring.c	include/linux/list.h	INIT_LIST_HEAD	7
io_uring.c	include/linux/list.h	LIST_HEAD	14
io_uring.c	include/linux/workqueue.h	INIT_WORK	1
io_uring.c	include/linux/workqueue.h	INIT_DELAYED_WORK	1
io_uring.c	include/linux/bug.h	WARN_ON_ONCE	16
io_uring.c	include/linux/bug.h	BUG_ON	18
io_uring.c	include/linux/bug.h	BUILD_BUG_ON	16
io_uring.c	include/linux/kernel.h	READ_ONCE	34
io_uring.c	include/linux/kernel.h	WRITE_ONCE	11
io_uring.c	include/linux/kernel.h	ALIGN	4
io_uring.c	include/linux/kernel.h	BIT	45
io_uring.c	include/linux/stat.h	S_ISREG	1
io_uring.c	include/linux/stat.h	S_ISBLK	1
io_uring.c	include/linux/mm.h	PAGE_ALIGN	2
io_uring.c	include/linux/wait.h	DEFINE_WAIT	1
io_uring.c	include/linux/jump_label.h	DEFINE_STATIC_KEY_FALSE	1
io_uring.c	io_uring.c	__io_cq_lock	3
io_uring.c	io_uring.c	__io_commit_cqring_flush	1
io_uring.c	io_uring.c	io_cqring_ev_events	14
io_uring.c	io_uring.c	io_uring_add_tctx_node	2
io-wq.c	linux/refcount.h	refcount_inc_not_zero	2
io-wq.c	linux/refcount.h	refcount_dec_and_test	2
io-wq.c	linux/sched.h	wake_up_process	2
io-wq.c	linux/sched.h	set_task_comm	1
io-wq.c	linux/sched.h	signal_pending	1
io-wq.c	linux/sched.h	__set_current_state	3
io-wq.c	linux/atomic.h	atomic_inc	4
io-wq.c	linux/atomic.h	atomic_dec	3
io-wq.c	linux/atomic.h	atomic_dec_and_test	2
io-wq.c	linux/atomic.h	atomic_or	2
io-wq.c	linux/atomic.h	atomic_read	2
io-wq.c	linux/completion.h	init_completion	1
io-wq.c	linux/completion.h	wait_for_completion	2
io-wq.c	linux/completion.h	complete	2
io-wq.c	linux/slab.h	kzalloc	1
io-wq.c	linux/slab.h	kfree	7
io-wq.c	linux/slab.h	kmalloc	1
io-wq.c	linux/rcupdate.h	rcu_read_lock	4
io-wq.c	linux/rcupdate.h	rcu_read_unlock	4
io-wq.c	linux/cpumask.h	cpumask_test_cpu	1
io-wq.c	linux/cpumask.h	cpumask_set_cpu	1
io-wq.c	linux/cpumask.h	cpumask_clear_cpu	1
io-wq.c	linux/cpumask.h	cpumask_subset	1
io-wq.c	linux/cpumask.h	cpumask_copy	2
io-wq.c	linux/task_work.h	task_work_add	1
io-wq.c	linux/task_work.h	task_work_cancel_match	2
io-wq.c	linux/wait.h	__add_wait_queue	1
io-wq.c	linux/wait.h	wake_up	2
io-wq.c	linux/workqueue.h	schedule_delayed_work	1
io-wq.c	linux/workqueue.h	INIT_DELAYED_WORK	1
io-wq.c	linux/string.h	memset	1
io-wq.c	linux/signal.h	__set_notify_signal	2
io-wq.c	linux/sched/signal.h	fatal_signal_pending	1
io-wq.c	linux/kernel.h	WARN_ON_ONCE	2
io-wq.c	linux/kernel.h	pr_warn_once	1
io-wq.c	linux/kernel.h	container_of	10
io-wq.c	linux/mm.h	kasan_mempool_unpoison_object	1
io-wq.c	io-wq.h	io_wq_current_is_worker	1
io-wq.c	io-wq.h	io_wq_work_match_all	1
io-wq.c	io-wq.h	io_wq_hash_work	1
io-wq.c	slist.h	wq_list_add_tail	2
io-wq.c	slist.h	wq_list_del	3
io-wq.c	slist.h	wq_list_for_each	2
io-wq.c	io_uring.h	create_io_thread	2
io-wq.c	io-wq.c (internal)	create_io_worker	4
io-wq.c	io-wq.c (internal)	io_wq_worker	1
io-wq.c	io-wq.c (internal)	io_wq_enqueue	2
io-wq.c	io-wq.c (internal)	io_wq_cancel_pending_work	2
io-wq.c	io-wq.c (internal)	io_worker_exit	1
io-wq.c	io-wq.c (internal)	io_worker_release	5
io-wq.c	io-wq.c (internal)	io_wq_dec_running	3
io-wq.c	io-wq.c (internal)	io_acct_run_queue	2
io_uring.h	linux/string.h	memcpy	3
io_uring.h	linux/string.h	memset	2
io_uring.h	linux/slab.h	kzalloc	1
io_uring.h	linux/slab.h	kfree	1
io_uring.h	linux/sched.h	wake_up_process	1
io_uring.h	linux/sched.h	__set_current_state	4
io_uring.h	linux/sched.h	resume_user_mode_work	1
io_uring.h	linux/sched.h	task_work_pending	2
io_uring.h	linux/sched.h	task_work_run	1
io_uring.h	linux/atomic.h	smp_store_release	1
io_uring.h	linux/atomic.h	smp_load_acquire	1
io_uring.h	linux/wait.h	__wake_up	2
io_uring.h	linux/wait.h	wq_has_sleeper	2
io_uring.h	linux/kernel.h	container_of	5+
io_uring.h	linux/kernel.h	WARN_ON_ONCE	2
io_uring.h	linux/kernel.h	min	1
io_uring.h	linux/compiler.h	unlikely	6+
io_uring.h	linux/compiler.h	likely	2
io_uring.h	linux/lockdep.h	lockdep_assert_held	3
io_uring.h	linux/errno.h	EAGAIN, EIOCBQUEUED	2
io_uring.h	linux/poll.h	poll_to_key	2
io_uring.h	linux/eventpoll.h	EPOLLIN, EPOLL_URING_WAKE	2
io_uring.h	uapi/linux/io_uring.h	struct io_uring_params	1
io_uring.h	asm/barrier.h	smp_mb	1
io_uring.h	io-wq.h	io_wq_free_work	1
io_uring.h	io-wq.h	io_wq_submit_work	1
io_uring.h	alloc_cache.h	io_cache_alloc	1
io_uring.h	slist.h	wq_list_add_tail	2
io_uring.h	slist.h	wq_stack_extract	1
io_uring.h	io_uring.h (internal)	io_lockdep_assert_cq_locked	4+
io_uring.h	io_uring.h (internal)	io_req_task_work_add	3+
io_uring.h	io_uring.h (internal)	io_fill_cqe_req	1
io_uring.h	io_uring.h (internal)	io_get_cqe	2
io_uring.h	io_uring.h (internal)	io_commit_cqring	1
io_uring.h	io_uring.h (internal)	io_req_complete_defer	1
io_uring.h	io_uring.h (internal)	io_uring_alloc_async_data	1
io_uring.h	io_uring.h (internal)	io_put_file	1
io_uring.h	io_uring.h (internal)	io_ring_submit_lock	1
io_uring.h	io_uring.h (internal)	io_ring_submit_unlock	1
io_uring.h	io_uring.h (internal)	io_poll_wq_wake	1
io_uring.h	io_uring.h (internal)	io_cqring_wake	1
sqpoll.c	linux/kernel.h	WARN_ON_ONCE	4
sqpoll.c	linux/kernel.h	READ_ONCE	1
sqpoll.c	linux/kernel.h	container_of	1
sqpoll.c	linux/slab.h	kzalloc	1
sqpoll.c	linux/slab.h	kfree	2
sqpoll.c	linux/sched.h	wake_up_process	2
sqpoll.c	linux/sched.h	set_task_comm	1
sqpoll.c	linux/sched.h	signal_pending	3
sqpoll.c	linux/sched.h	__set_current_state	1
sqpoll.c	linux/refcount.h	refcount_dec_and_test	1
sqpoll.c	linux/refcount.h	refcount_inc	1
sqpoll.c	linux/atomic.h	atomic_inc	1
sqpoll.c	linux/atomic.h	atomic_dec_return	1
sqpoll.c	linux/atomic.h	atomic_andnot	1
sqpoll.c	linux/atomic.h	atomic_or	3
sqpoll.c	linux/completion.h	init_completion	1
sqpoll.c	linux/completion.h	complete	2
sqpoll.c	linux/wait.h	wait_event	1
sqpoll.c	linux/wait.h	prepare_to_wait	2
sqpoll.c	linux/wait.h	finish_wait	2
sqpoll.c	linux/mutex.h	mutex_lock	7
sqpoll.c	linux/mutex.h	mutex_unlock	6
sqpoll.c	linux/list.h	list_for_each_entry	4
sqpoll.c	linux/list.h	list_add	1
sqpoll.c	linux/list.h	list_del_init	1
sqpoll.c	linux/cpumask.h	cpumask_of	1
sqpoll.c	linux/cpumask.h	cpumask_test_cpu	1
sqpoll.c	linux/cred.h	override_creds	1
sqpoll.c	linux/cred.h	revert_creds	1
sqpoll.c	linux/security.h	security_uring_sqpoll	1
sqpoll.c	linux/audit.h	audit_uring_entry	1
sqpoll.c	linux/audit.h	audit_uring_exit	1
sqpoll.c	uapi/linux/io_uring.h	struct io_uring_params	2
sqpoll.c	io_uring.h	io_uring_alloc_task_context	1
sqpoll.c	io_uring.h	io_uring_cancel_generic	1
sqpoll.c	io_uring.h	io_run_task_work	1
sqpoll.c	io_uring.h	create_io_thread	1
sqpoll.c	napi.h	io_napi	1
sqpoll.c	napi.h	io_napi_sqpoll_busy_poll	1
sqpoll.c	sqpoll.c (internal)	io_sq_thread_unpark	2
sqpoll.c	sqpoll.c (internal)	io_sq_thread_park	3
sqpoll.c	sqpoll.c (internal)	io_sq_thread_stop	1
sqpoll.c	sqpoll.c (internal)	io_put_sq_data	1
sqpoll.c	sqpoll.c (internal)	io_sqd_update_thread_idle	2
sqpoll.c	sqpoll.c (internal)	io_sq_thread_finish	2

Continue with the list untill all functions used in each source are listed.
