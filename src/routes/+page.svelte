<script lang="ts">
	import { Button } from "$lib/components/ui/button";
	import * as Sheet from "$lib/components/ui/sheet";
	import add from '$lib/images/Add_round_duotone.svg';
	import done from '$lib/images/Done_round_duotone.svg';
	import pencil from '$lib/images/Edit_duotone.svg';
	import logo from '$lib/images/Logo.svg';
	import loading from '$lib/images/Time_atack_duotone.svg';
	import remove from '$lib/images/close_ring_duotone.svg';
	import { Check, Trash } from 'lucide-svelte';
</script>

<div class="w-[30rem]">
	<div class="flex items-start justify-start gap-3">
		<img src={logo} alt="Logo">
		<h1 class="text-4xl font-semibold mb-4"> My Task Board</h1>
		<img src={pencil} alt="Pencil">
	</div>
	<p class="font-semibold">Tasks to keep organised</p>

	<div class="my-8 flex flex-col gap-4">

		<!-- In progress -->
		<div class="flex items-center cursor-pointer gap-6 bg-[#F5D565] p-4 rounded-xl">
			<div class="bg-white w-12 h-12 flex items-center justify-center rounded-lg text-2xl">⏰</div>
			<h2 class="text-xl font-semibold flex-1">Task in Progress</h2>
			
			<!-- icon -->
			<div class="bg-[#E9A23B] w-12 h-12 flex items-center justify-center justify-self-end place-self-end self-end rounded-lg">
				<img src={loading} alt="">
			</div>
		</div>

		<!-- Completed -->
		<div class="flex items-center cursor-pointer gap-6 bg-[#A0ECB1] p-4 rounded-xl">
			<div class="bg-white w-12 h-12 flex items-center justify-center rounded-lg text-2xl">🏋️‍♂️</div>
			<h2 class="text-xl font-semibold flex-1">Task Completed</h2>

			<!-- icon -->
			<div class="bg-[#32D657] w-12 h-12 flex items-center justify-center justify-self-end place-self-end self-end rounded-lg">
				<img src={done} alt="">
			</div>
			
		</div>

		<!-- Won't do -->
		<div class="flex items-center cursor-pointer gap-6 bg-[#F7D4D3] p-4 rounded-xl">
			<div class="bg-white w-12 h-12 flex items-center justify-center rounded-lg text-2xl">☕</div>
			<h2 class="text-xl font-semibold flex-1">Task Won't Do</h2>

			<div class="bg-[#DD524C] w-12 h-12 flex items-center justify-center rounded-lg">
				<img src={remove} alt="">
			</div>
		</div>

		<!-- To do -->
		<div class="flex items-start cursor-pointer gap-6 bg-[#E3E8EF] p-4 rounded-xl">
			<div class="bg-white w-12 h-12 flex items-center justify-center rounded-lg text-2xl">📚</div>
			<div>
				<h2 class="text-xl font-semibold mb-1">Task To Do</h2>
				<p>Work on a challenge on devChallenges.io learn typescript</p>
			</div>
		</div>

		<!-- Add new task -->
		<Sheet.Root>
			<Sheet.Trigger>
				<div class="flex items-center cursor-pointer gap-6 bg-[#F5E8D5] p-4 rounded-xl">
					<div class="bg-[#E9A23B] w-12 h-12 flex items-center justify-center rounded-xl text-4xl">
						<img src={add} alt="">
					</div>
					<h2 class="text-xl font-semibold mb-1">Add new task</h2>
				</div>
			</Sheet.Trigger>
			<Sheet.Content class="w-[50rem]">
				<Sheet.Header>
					<Sheet.Title>Task details</Sheet.Title>
				</Sheet.Header>

				<div>
					<Button class="text-sm bg-[#97A3B6] rounded-3xl px-8 py-2 gap-2">
						Delete
						<Trash size={18} />
					</Button>
					<Button class="text-sm bg-[#3662E3] rounded-3xl px-8 py-2 gap-2">
						Save
						<Check size={20} />
					</Button>
				</div>
			</Sheet.Content>
		</Sheet.Root>
	</div>
</div>
