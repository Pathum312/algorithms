<script lang="ts">
	import {
		Card,
		Header,
		Footer,
		Content,
		Section,
		CardTitle,
		CardDescription,
	} from '$lib/components/ui';
</script>

<title>Algorithms</title>
<Header align="center">Algorithms</Header>
<Content>
	<Section title="Sorting Algorithms">
		<Card>
			<CardTitle>Selection Sort</CardTitle>
			<CardDescription
				>Selection sort is a simple and efficient sorting algorithm that works by repeatedly
				selecting the smallest (or largest) element from the unsorted portion of the list and moving
				it to the sorted portion of the list.
			</CardDescription>
		</Card>
		<Card>
			<CardTitle>Bubble Sort</CardTitle>
			<CardDescription>
				In Bubble Sort algorithm, traverse from left and compare adjacent elements and the higher
				one is placed at right side. In this way, the largest element is moved to the rightmost end
				at first. This process is then continued to find the second largest and place it and so on
				until the data is sorted.
			</CardDescription>
		</Card>
		<Card>
			<CardTitle>Merge Sort</CardTitle>
			<CardDescription>
				Merge Sort tackles a messy list like a master organizer. It divides the list in half
				repeatedly until it reaches single elements (already sorted sub-lists). Then, it cleverly
				merges these sorted sub-lists back together, comparing elements from each half and placing
				the smaller one into the final sorted list. This <b>"divide-and-conquer"</b> strategy makes Merge
				Sort a fast and efficient way to sort information, working like a pro at shuffling smaller sorted
				chunks into a single, perfectly organized list.
			</CardDescription>
		</Card>
	</Section>
	<Section title="Searching Algorithms">
		<Card>
			<CardTitle>Selection Sort</CardTitle>
			<CardDescription
				>Selection sort is a simple and efficient sorting algorithm that works by repeatedly
				selecting the smallest (or largest) element from the unsorted portion of the list and moving
				it to the sorted portion of the list.
			</CardDescription>
		</Card>
		<Card>
			<CardTitle>Bubble Sort</CardTitle>
			<CardDescription>
				In Bubble Sort algorithm, traverse from left and compare adjacent elements and the higher
				one is placed at right side. In this way, the largest element is moved to the rightmost end
				at first. This process is then continued to find the second largest and place it and so on
				until the data is sorted.
			</CardDescription>
		</Card>
		<Card>
			<CardTitle>Merge Sort</CardTitle>
			<CardDescription>
				Merge Sort tackles a messy list like a master organizer. It divides the list in half
				repeatedly until it reaches single elements (already sorted sub-lists). Then, it cleverly
				merges these sorted sub-lists back together, comparing elements from each half and placing
				the smaller one into the final sorted list. This 'divide-and-conquer' strategy makes Merge
				Sort a fast and efficient way to sort information, working like a pro at shuffling smaller
				sorted chunks into a single, perfectly organized list.
			</CardDescription>
		</Card>
	</Section>
</Content>
<Footer align="center">© 2024 Pathum Senanayake</Footer>
