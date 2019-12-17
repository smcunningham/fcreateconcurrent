# fcreateconcurrent

We will write a program that creates 100 goroutines. Each of these goroutines will generate a random number concurrently, thus generating one hundred random numbers in total. These random numbers will be written to a file. We will solve this problem by using the following approach:

Create a channel which will be used to read and write the generated random numbers.

Create 100 producer goroutines. Each goroutine will generate a random number and will also write the random number to a channel.

Create a consumer goroutine which will read from the channel and write the generated random number to the file. Thus we have only one goroutine writing to a file concurrently, which avoids a race condition.

Close the file once done.