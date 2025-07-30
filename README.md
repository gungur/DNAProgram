# DNA Transcription and Translation Program

This program provides a complete implementation of the central dogma of molecular biology (DNA → RNA → Protein) using fundamental data structures, demonstrating how biological processes can be modeled computationally.

## Overview

This Java program implements DNA transcription and translation using a linked queue data structure. It can:
- Transcribe DNA sequences into mRNA
- Translate mRNA sequences into amino acid chains (proteins)
- Handle the entire process from DNA to protein sequence

## Classes

### 1. DNA Class
The main class that performs DNA transcription and translation operations.

**Key Methods:**
- `transcribeDNA()`: Converts DNA to mRNA
- `mRNATranslate()`: Translates mRNA to amino acids
- `translateDNA()`: Combines both processes (DNA → mRNA → protein)

### 2. LinkedQueue Class
A generic queue implementation using linked nodes that supports:
- Enqueue (add to back)
- Dequeue (remove from front)
- Peek (view front element)
- Size checking
- Empty checking

### 3. Node Class
The basic building block for the linked queue implementation.

### 4. QueueADT Interface
Defines the standard queue operations that LinkedQueue implements.

### 5. DNATester Class
Contains test cases to verify the functionality of the DNA processing system.

## How It Works

1. **DNA Transcription**:
   - Converts DNA bases to complementary mRNA bases (A→U, T→A, C→G, G→C)
   - Preserves the original DNA sequence

2. **mRNA Translation**:
   - Processes mRNA in codons (3-base sequences)
   - Uses a codon-to-amino-acid mapping table
   - Stops translation when encountering a STOP codon

## Usage Example

```java
// Create a DNA sequence
DNA dnaSequence = new DNA("GGAGTCAGTTAAGCGACCGGGACATACTGTCTTGGTAATCTCCGAGCTAGAAAGTCTCTG");

// Transcribe to mRNA
LinkedQueue<Character> mRNA = dnaSequence.transcribeDNA();

// Translate to amino acids
LinkedQueue<String> protein = dnaSequence.translateDNA();

System.out.println("mRNA: " + mRNA.toString());
System.out.println("Protein: " + protein.toString());
```

## Testing

The DNATester class includes comprehensive test cases for:
- DNA transcription
- mRNA translation
- Combined DNA translation
- Queue operations (enqueue, dequeue, size, etc.)

Run the tests with:
```java
public static void main(String[] args) {
    System.out.println("transcribeDNA: " + testTranscribeDNA());
    System.out.println("translateDNA: " + testTranslateDNA());
    System.out.println("mRNATranslate: " + testMRNATranslate());
    System.out.println("EnqueueDequeue: " + testEnqueueDequeue());
    System.out.println("QueueSize: " + testQueueSize());
}
```

## Implementation Details

- Uses linked nodes for efficient queue operations
- Maintains original DNA sequence after transcription
- Handles edge cases (empty queues, incomplete codons)
- Includes comprehensive error checking

## Requirements

- Java 8 or higher
- No external dependencies
