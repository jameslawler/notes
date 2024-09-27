## c#

```c#
using System;
using System.Collections.Generic;

public class Song
{
    private string name;
    public Song NextSong { get; set; }

    public Song(string name)
    {
        this.name = name;
    }

    public bool IsInRepeatingPlaylist()
    {
        Dictionary<Song, bool> seenSongs = new Dictionary<Song, bool>();

        Song currentSong = this;
        seenSongs.Add(currentSong, true);

        while (currentSong.NextSong != null && !seenSongs.ContainsKey(currentSong.NextSong))
        {
            currentSong = currentSong.NextSong;
            seenSongs.Add(currentSong, true);
        }

        return currentSong.NextSong != null;
    }

    public static void Main(string[] args)
    {
        Song first = new Song("Hello");
        Song second = new Song("Eye of the tiger");

        first.NextSong = second;
        second.NextSong = first;

        Console.WriteLine(first.IsInRepeatingPlaylist());
    }
}
```

```c++
#include <stdexcept>
#include <iostream>
#include <map>

class Song
{
public:
    Song(std::string name): name(name), nextSong(NULL) {}

    void next(Song* song)
    {
        this->nextSong = song;
    }

    bool isInRepeatingPlaylist()
    {
        std::map<std::string, bool> seenSongs;

        Song* currentSong = this;
        seenSongs.insert(std::pair<Song**, bool>(&currentSong, true));

        while (currentSong->nextSong != NULL && !seenSongs.contains(&currentSong->nextSong))
        {
            currentSong = currentSong->nextSong;
            seenSongs.insert(std::pair<Song**, bool>(&currentSong, true));
        }

        return currentSong->nextSong != NULL;
    }

private:
    const std::string name;
    Song* nextSong;
};

#ifndef RunTests
int main()
{
    Song* first = new Song("Hello");
    Song* second = new Song("Eye of the tiger");

    first->next(second);
    second->next(first);

    std::cout << std::boolalpha << first->isInRepeatingPlaylist();
}
#endif
```
